<template>
  <div class="live-container">
    <ChannelStats />
    <LiveChat />
  </div>
</template>

<script>
import ChannelStats from '@/components/ChannelStats'
import LiveChat from '@/components/LiveChat'
export default {
  components: [ChannelStats, LiveChat],
  layout: null,
}
</script>

<style scoped>
.live-container {
  background-color: #111111;
}
</style>
