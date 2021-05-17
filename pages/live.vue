<template>
  <div id="live-container">
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
#live-container {
  width: 1920px;
  height: 1080px;
  background-color: #f2f2f2;
}
</style>
