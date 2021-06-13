<template>
  <div class="livechat-container">
    <p v-if="error && error !== ''" id="error-message"></p>
    <div v-for="message in messages" v-else :key="message.messageId">
      <div v-if="!message.isArchived" class="message-container">
        <img class="author-avata" :src="message.avatarUrl" />
        <div class="text-container">
          <div class="author-info">
            {{ message.authorName }} {{ message.authorRole }}
          </div>
          <p class="message-text">{{ message.text }}</p>
        </div>
        <button
          class="button-archive"
          @click="archiveMessage(message.messageId)"
        >
          <img src="~/assets/img/icon_archive.svg" alt="" />
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      messages: [],
      authors: [],
      error: '',
      socket: null,
    }
  },
  async mounted() {
    this.socket = this.$nuxtSocket({ name: 'main' })
    const isInitialized = await this.initialize()
    if (!isInitialized) {
      // this.error = 'Failed to initialize livechat manager'
    } else {
      await this.fetchAuthors()
      await this.fetchMessages()

      this.socket.on('New author', this.newAuthorEventHandler)
      this.socket.on('New message', this.newMessageEventHandler)
    }
  },
  methods: {
    async fetchMessages() {
      const res = await this.$axios.get(
        'http://localhost:3458/api/v1/live-chat/messages'
      )
      const newMessages = res.data
      this.messages = this.mapMessages(newMessages)
    },
    async fetchAuthors() {
      const res = await this.$axios.get(
        'http://localhost:3458/api/v1/live-chat/authors'
      )
      const newAuthors = res.data
      this.authors = newAuthors
    },
    mapMessages(messages) {
      const authors = [...this.authors]
      return messages.map((message) => {
        const author = authors.find(
          ({ channelId }) => channelId === message.authorId
        )
        console.log(author)
        const { avatarUrl, name: authorName, role: authorRole } = author
        return {
          ...message,
          avatarUrl,
          authorName,
          authorRole,
        }
      })
    },
    newAuthorEventHandler(author) {
      this.authors.push(author)
    },
    newMessageEventHandler(newMessage) {
      console.log(newMessage)
      const author = this.authors.find(
        ({ channelId }) => channelId === newMessage.authorId
      )
      const { avatarUrl, name: authorName, role: authorRole } = author
      const parsedMessage = {
        ...newMessage,
        avatarUrl,
        authorName,
        authorRole,
      }

      this.messages.unshift(parsedMessage)
    },
    async archiveMessage(messageId) {
      const messageIndex = this.messages.findIndex(
        (message) => message.messageId === messageId
      )
      if (messageIndex === -1) {
        return
      }
      this.messages[messageIndex].isArchived = true
      this.$forceUpdate()
      const res = await this.$axios.get(
        `http://localhost:3458/api/v1/live-chat/messages/${messageId}/archive`
      )
      if (!res.data) {
        this.messages[messageIndex].isArchived = false
        this.$forceUpdate()
      }
    },
    async initialize() {
      const res = await this.$axios.get(
        `http://localhost:3458/api/v1/live-chat/init`
      )
      return res.data
    },
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat&display=swap');

:root {
  --font-root: 'Montserrat', sans-serif;
  --background: #111111;
  --background-header: #2c2c2c;
  --background-message: #2c2c2c;
  --author-name-color: #fff1dc;
  --message-text-color: rgba(255, 255, 255, 0.9);
}

.livechat-container {
  font-family: var(--font-root);
  width: 376px;
  max-height: 765px;
  font-size: 11px;
  overflow-y: auto;
  overflow-x: hidden;
  background-color: var(--background);
  margin: 15px;
}

.message-container {
  display: flex;
  flex-direction: row;
  align-items: center;
  min-width: 20.75rem;
  margin: 1.25rem 1.5rem;
  padding: 0.75rem;
  background-color: var(--background-message);
  border-radius: 7px;
  animation: 0.25s ease-out 0s 1 slideDown;
}

@keyframes slideDown {
  0% {
    transform: translateY(-100%);
  }
  100% {
    transform: translateY(0);
  }
}

.message-container:hover {
  transform: scale(1.05);
  transition: all 0.5s;
}

.author-info {
  color: var(--author-name-color);
  font-weight: 500;
}

.author-info img {
  width: 30px;
  height: 30px;
  margin-right: 20px;
}

.message-text {
  color: var(--message-text-color);
  width: 220px;
  word-break: break-word;
}

.author-avata {
  border-radius: 50%;
  width: 2.125rem;
  height: 2.125rem;
  margin: auto 0.75rem;
}

.button-archive {
  background-color: var(--background-message);
  all: unset;
  margin-left: auto;
  margin-right: 0.25rem;
  cursor: pointer;
}

.button-archive:hover {
  transform: scale(1.1);
  transition: all 0.5s;
}
</style>
