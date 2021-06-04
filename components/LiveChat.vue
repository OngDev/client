<template>
  <div class="livechat-container">
    <p v-if="error && error !== ''" id="error-message"></p>
    <div
      v-for="message in messages"
      v-else
      :key="message.messageId"
      class="message-container"
    >
      <img class="author-avata" :src="message.avatarUrl" />
      <div class="text-container">
        <div class="author-info">
          {{ message.authorName }} {{ message.authorRole }}
        </div>
        <p class="message-text">{{ message.text }}</p>
      </div>
      <button class="button-archive" @click="archiveMessage(message.id)">
        <img src="~/assets/img/icon_archive.svg" alt=""/>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      messages: [
        {
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI6ChpDSTIyX3ItVDJfQUNGZFlJclFZZFRYOEw1ZxIcQ0lTVndLU1QyX0FDRlFSaldBb2RaUGtPSVEtMQ',
          text: 'Nên đi ngủ ạ :))',
          authorId: 'UCClOqkmKvLwD756KLr78qBQ',
          publishedAt: '2021-05-21T16:04:46.743367+00:00',
          messageType: 'text',
          isResolved: false,
          _id: '60a7da23ba8b833cdcde5145',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhMgwhcevDdQ4G-s90vW6cG96-T8OwAreuJFYeGow=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Chau Dang',
          authorRole: '👶',
        },
        {
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDUEQyNFlHUjJfQUNGU2dIclFZZExJa0UwdxIbQ0lPWW1KNk4yX0FDRllkOFdBb2RtM2tDS1Ew',
          text: 'SSO',
          authorId: 'UCi742f1D24kyihZZCuT07VA',
          publishedAt: '2021-05-21T15:53:39.382169+00:00',
          messageType: 'text',
          isResolved: false,
          _id: '60a7d786ba8b833cdcde5143',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhqN8p3axsTcLoXbYKh7IwNmuslpiGoBx7FrQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Bummm Kim zj',
          authorRole: '👶',
        },
        {
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTFhReWF5UTJfQUNGZE1OZlFvZEw4b041dxIbQ01UZWhZMlEyX0FDRlE4T3R3QWRBVDRIR0Ew',
          text: 'lý do nào khiến ông dev chọn nest để build backend vậy . cty em đang cân nhắc chuyển hệ thống qua nest . em đang beginer mong nhận lời khuyên của anh về nest',
          authorId: 'UC80IZHeivsaZyB2TuvZk-_w',
          publishedAt: '2021-05-21T15:50:40.72612+00:00',
          messageType: 'text',
          isResolved: false,
          _id: '60a7d6d3ba8b833cdcde5141',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwng0X76VSSWEcBHE5--n8NVYwj3YdaZJJnYYhadF=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Kiet Tuan',
          authorRole: '👶',
        },
        {
          _id: '60a7d1d1f2d030539874bb34',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTFNMcHYtSzJfQUNGWUFrclFZZGJrVU5LURIbQ05uUDdNdjIydkFDRmY3TFRBSWRoa1lCVFEy',
          text: 'rap hay quá anh ơi :)))',
          authorId: 'UCvcYWNuyAY4gTHfhDoQXuDg',
          publishedAt: '2021-05-21T15:26:43.594746+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhl3NsUAfxpJkXMIml4uWZMtOykuX0d1qj1QYGa8Q=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Đinh Sỹ Hùng',
          authorRole: '👶',
        },
        {
          _id: '60a7d1d1f2d030539874bb33',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI6ChpDTUdWemVXSzJfQUNGZE1OZlFvZEw4b041dxIcQ1BUUXk4aUsyX0FDRlJKUFdBb2RwNEFES2ctMA',
          text: 'Em sắp tới đi học CNTT ở BTEC FPT thì em nên laptop như thế nào ạ',
          authorId: 'UCMLBzrtcoRqV5nxo46wy-Mg',
          publishedAt: '2021-05-21T15:25:49.709033+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh41hkVuloEz5Xlv0wX1GhzmF5omq0bbjvWtGHMZg=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Vũ Bảo Phúc',
          authorRole: '👶',
        },
        {
          _id: '60a7d077f2d030539874bb31',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDUFRBMUtLSzJfQUNGZFlJclFZZFRYOEw1ZxIbQ0p5QV84LUYyX0FDRllkaVlBb2Q2S1VFUmcy',
          text: 'cái repo youtube livechat archive hỉ ông dev?',
          authorId: 'UCLAeh5SDjUBOjnE8HTXJLGw',
          publishedAt: '2021-05-21T15:23:29.320106+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjeWisuPPm3gtioXItdBEPzbXpNfc3e2ZgyggjK2Xo=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thuan Pham',
          authorRole: '🔧',
        },
        {
          _id: '60a7cf81f2d030539874bb30',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTUtic0s2SjJfQUNGVVFRclFZZG9Ra09qdxIbQ0lxa2c3YUMyX0FDRllncFdBb2R3ZE1FaFEz',
          text: 'em thấy nhiều lúc nó kiểu thế đấy ạ',
          authorId: 'UCcPr9sZBQZljTe9u03wCRIA',
          publishedAt: '2021-05-21T15:19:25.45585+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniUOg4HTMZZQW8WUJDLo10FscZ-h3oKN3V7XmLBKA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'FL• Olafff',
          authorRole: '🔧',
        },
        {
          _id: '60a7cf7cf2d030539874bb2f',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSWVYMWF1SjJfQUNGZmtGclFZZE1jb0dZURIbQ0tLLXZNdUkyX0FDRlJkU1dBb2QwUDRHa1Ew',
          text: 'vì nó chưa được uống bia. Nó cần bia :v',
          authorId: 'UCJDMX31jsUomae5GuSO-1sg',
          publishedAt: '2021-05-21T15:19:19.770095+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjxykSC5iADe6vU1-EpYW9feQQ0FHTbS1rrzQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Công Nam Lê',
          authorRole: '👶',
        },
        {
          _id: '60a7cf6cf2d030539874bb2d',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTlBNcEtXSjJfQUNGYVlfclFZZE9BY0dLQRIbQ0piOGxjUF8ydkFDRlZBZ0tnb2QwSGtLN1E0',
          text: 'lên mà chậm',
          authorId: 'UCLLp4QBHeG9OITLG8eD5L6A',
          publishedAt: '2021-05-21T15:19:06.391203+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhQ9bo-n6PXceLLKApohDFZczX8EFMd0sHAz4I-sQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thảo Y',
          authorRole: '👶',
        },
        {
          _id: '60a7cf6cf2d030539874bb2c',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSnVEcXFTSjJfQUNGVVFRclFZZG9Ra09qdxIbQ0lhOHdlNzkydkFDRlpKWGhRb2R1ZDRISmcw',
          text: 'my check',
          authorId: 'UCOkMGmtjw6-oTweKEB9Ll2g',
          publishedAt: '2021-05-21T15:19:04.382909+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhu5SPig7qTr9C_3Sm-QSACP8OITXnU57TZxw=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Nhã Nguyễn',
          authorRole: '👶',
        },
        {
          _id: '60a7cf67f2d030539874bb2a',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDT3lpX3FLSjJfQUNGU0lHNXdvZGE4Y0N4QRIbQ0lxa2c3YUMyX0FDRllncFdBb2R3ZE1FaFEy',
          text: 'lên r mà',
          authorId: 'UCcPr9sZBQZljTe9u03wCRIA',
          publishedAt: '2021-05-21T15:19:01.568942+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniUOg4HTMZZQW8WUJDLo10FscZ-h3oKN3V7XmLBKA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'FL• Olafff',
          authorRole: '🔧',
        },
        {
          _id: '60a7cf5cf2d030539874bb29',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDUGVpNzV5SjJfQUNGWUVYZlFvZGVkd0dzURIbQ0xUOC1zVDQydkFDRlVVMVdBb2RBMHNLTlEw',
          text: 'hú hú',
          authorId: 'UCdxahxK0f7OVofmWVQHf0Aw',
          publishedAt: '2021-05-21T15:18:48.740265+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwni6KCwNpA_5SRH9WcaqatgH43DG7MY8C3pZ7A=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Văn Thử Nguyễn',
          authorRole: '👶',
        },
        {
          _id: '60a7cf58f2d030539874bb27',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSUM0clpxSjJfQUNGZWtsclFZZHdESUtZQRIbQ01yYzMtaUcyX0FDRllkRDlRVWRSSWdOWGcx',
          text: 'oke a',
          authorId: 'UCi8KhS98bLc-3Lw3oCrPmvA',
          publishedAt: '2021-05-21T15:18:43.467297+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhW5zJ1uNaEg2wSU0mumm-YJIymVtTe1N2VRtm9HXc=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Nguyễn Công Khanh',
          authorRole: '👶',
        },
        {
          _id: '60a7cf58f2d030539874bb26',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSVQ2MHBtSjJfQUNGZWtsclFZZHdESUtZQRIbQ1B2MXk0UDgydkFDRlI5QTlRVWRILUVMVXcw',
          text: 'asd',
          authorId: 'UCA2tFk2NdzOzKpSJdf24cAg',
          publishedAt: '2021-05-21T15:18:41.98482+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniUCEs24rFdyoW2EMl0p6M-PtQfAJfMIHqW1bXr=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Ông Dev',
          authorRole: '👑',
        },
        {
          _id: '60a7cf52f2d030539874bb25',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTGZHbHBpSjJfQUNGYVlfclFZZE9BY0dLQRIbQ0lxa2c3YUMyX0FDRllncFdBb2R3ZE1FaFEx',
          text: 'hú',
          authorId: 'UCcPr9sZBQZljTe9u03wCRIA',
          publishedAt: '2021-05-21T15:18:38.89801+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniUOg4HTMZZQW8WUJDLo10FscZ-h3oKN3V7XmLBKA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'FL• Olafff',
          authorRole: '🔧',
        },
        {
          _id: '60a7cf52f2d030539874bb24',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDT1gtX0phSjJfQUNGU2dIclFZZExJa0UwdxIbQ0p5QV84LUYyX0FDRllkaVlBb2Q2S1VFUmcx',
          text: 'ahihi',
          authorId: 'UCLAeh5SDjUBOjnE8HTXJLGw',
          publishedAt: '2021-05-21T15:18:36.382101+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjeWisuPPm3gtioXItdBEPzbXpNfc3e2ZgyggjK2Xo=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thuan Pham',
          authorRole: '🔧',
        },
        {
          _id: '60a7cf47f2d030539874bb23',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTlRCM0pPSjJfQUNGZE1OZlFvZEw4b041dxIbQ0p5QV84LUYyX0FDRllkaVlBb2Q2S1VFUmcw',
          text: '😀',
          authorId: 'UCLAeh5SDjUBOjnE8HTXJLGw',
          publishedAt: '2021-05-21T15:18:29.558538+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjeWisuPPm3gtioXItdBEPzbXpNfc3e2ZgyggjK2Xo=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thuan Pham',
          authorRole: '🔧',
        },
        {
          _id: '60a7cf18f2d030539874bb22',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDS0s3NlBxSTJfQUNGZWtsclFZZHdESUtZQRIbQ082XzRKajkydkFDRlVzUHR3QWRncW9DT0E0',
          text: 'hoặc await trước find chứ a nhỉ',
          authorId: 'UCWUmFpMtwi5JI02sjp7Hqwg',
          publishedAt: '2021-05-21T15:17:37.325503+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhZK6nfqdjLlJODziSW-X_3FXFg8LxHXUyu3gvsIQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Hiền Vương Phan Thái',
          authorRole: '👶',
        },
        {
          _id: '60a7cef3f2d030539874bb21',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTjNyNC1tSTJfQUNGWHdOclFZZC1iY0w1QRIbQ0tXUGw2YUYyX0FDRlUxSGhRb2RKcjRJMFEy',
          text: 'avatarUrl: avartarUrl',
          authorId: 'UC_SppENJpPrbQ504cRLarvA',
          publishedAt: '2021-05-21T15:17:01.598219+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniRyfGxPMgu3U9OXbxei_AYdx4v414jH3Gkr-L-DQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Kha Bui',
          authorRole: '👶',
        },
        {
          _id: '60a7cec3f2d030539874bb20',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI6ChpDUDZucE5XSTJfQUNGVVFRclFZZG9Ra09qdxIcQ0s3VnFhQ0cyX0FDRllOSGhRb2RzZzhCUnctMg',
          text: ':v',
          authorId: 'UC26CJlD2RHyLaeCO3E-tPdg',
          publishedAt: '2021-05-21T15:16:18.61432+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngcTk53kyrHg568e5yZ4XKLggB0g99wXJb_AHrTVA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thắng Phạm',
          authorRole: '👶',
        },
        {
          _id: '60a7ceb9f2d030539874bb1f',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI6ChpDTTJZMHMtSTJfQUNGZUFOclFZZGFpOEVZQRIcQ0s3VnFhQ0cyX0FDRllOSGhRb2RzZzhCUnctMQ',
          text: 'find trả về obj mà',
          authorId: 'UC26CJlD2RHyLaeCO3E-tPdg',
          publishedAt: '2021-05-21T15:16:06.783109+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngcTk53kyrHg568e5yZ4XKLggB0g99wXJb_AHrTVA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thắng Phạm',
          authorRole: '👶',
        },
        {
          _id: '60a7ceb9f2d030539874bb1e',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTTZpcTg2STJfQUNGVVFRclFZZG9Ra09qdxIbQ0tXUGw2YUYyX0FDRlUxSGhRb2RKcjRJMFEx',
          text: 'find id ra object',
          authorId: 'UC_SppENJpPrbQ504cRLarvA',
          publishedAt: '2021-05-21T15:16:04.048255+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniRyfGxPMgu3U9OXbxei_AYdx4v414jH3Gkr-L-DQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Kha Bui',
          authorRole: '👶',
        },
        {
          _id: '60a7ce9ff2d030539874bb1d',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSW5Ldk1HSTJfQUNGZG9XclFZZGs1Y09LQRIbQ082XzRKajkydkFDRlVzUHR3QWRncW9DT0Ey',
          text: 'hehe',
          authorId: 'UCWUmFpMtwi5JI02sjp7Hqwg',
          publishedAt: '2021-05-21T15:15:37.068857+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhZK6nfqdjLlJODziSW-X_3FXFg8LxHXUyu3gvsIQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Hiền Vương Phan Thái',
          authorRole: '👶',
        },
        {
          _id: '60a7ce7bf2d030539874bb1c',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSUxxeHJDSTJfQUNGZUFOclFZZGFpOEVZQRIbQ0xLOXNiai0ydkFDRmROU2hRb2RGcUVLVVEz',
          text: 'array.find là ra mảng chứ',
          authorId: 'UCkaTWNz-O4MDV6OzZqt7MJQ',
          publishedAt: '2021-05-21T15:15:01.585205+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh2ErRNzB-HAAVnVd8XM4Zg-riUYwkUKGpCTG_guQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Đỉnh Tiểu',
          authorRole: '👶',
        },
        {
          _id: '60a7ce41f2d030539874bb1b',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDT0Q2M3BhSTJfQUNGZFlJclFZZFRYOEw1ZxIbQ082XzRKajkydkFDRlVzUHR3QWRncW9DT0Ex',
          text: 'sao khúc author.find chạy được nhỉ :v',
          authorId: 'UCWUmFpMtwi5JI02sjp7Hqwg',
          publishedAt: '2021-05-21T15:14:07.454605+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhZK6nfqdjLlJODziSW-X_3FXFg8LxHXUyu3gvsIQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Hiền Vương Phan Thái',
          authorRole: '👶',
        },
        {
          _id: '60a7ce32f2d030539874bb1a',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSTZQX1kySTJfQUNGVVFRclFZZG9Ra09qdxIbQ0tXUGw2YUYyX0FDRlUxSGhRb2RKcjRJMFEw',
          text: 'avatarUrl chưa gán thì phải',
          authorId: 'UC_SppENJpPrbQ504cRLarvA',
          publishedAt: '2021-05-21T15:13:49.074354+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniRyfGxPMgu3U9OXbxei_AYdx4v414jH3Gkr-L-DQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Kha Bui',
          authorRole: '👶',
        },
        {
          _id: '60a7ce22f2d030539874bb19',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTTcyc0llSTJfQUNGZFlJclFZZFRYOEw1ZxIbQ0xLOXNiai0ydkFDRmROU2hRb2RGcUVLVVEy',
          text: 'trời',
          authorId: 'UCkaTWNz-O4MDV6OzZqt7MJQ',
          publishedAt: '2021-05-21T15:13:35.243133+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh2ErRNzB-HAAVnVd8XM4Zg-riUYwkUKGpCTG_guQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Đỉnh Tiểu',
          authorRole: '👶',
        },
        {
          _id: '60a7ce22f2d030539874bb18',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDS2FGNW9hSTJfQUNGZUFOclFZZGFpOEVZQRIbQ0xLOXNiai0ydkFDRmROU2hRb2RGcUVLVVEx',
          text: 'bien author là mảng',
          authorId: 'UCkaTWNz-O4MDV6OzZqt7MJQ',
          publishedAt: '2021-05-21T15:13:34.016219+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh2ErRNzB-HAAVnVd8XM4Zg-riUYwkUKGpCTG_guQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Đỉnh Tiểu',
          authorRole: '👶',
        },
        {
          _id: '60a7cde8f2d030539874bb16',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTzJyck95SDJfQUNGZmtGclFZZE1jb0dZURIbQ05uUDdNdjIydkFDRmY3TFRBSWRoa1lCVFEx',
          text: 'ơ bia anh làm uống được rồi à',
          authorId: 'UCvcYWNuyAY4gTHfhDoQXuDg',
          publishedAt: '2021-05-21T15:12:38.544918+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhl3NsUAfxpJkXMIml4uWZMtOykuX0d1qj1QYGa8Q=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Đinh Sỹ Hùng',
          authorRole: '👶',
        },
        {
          _id: '60a7cdb9f2d030539874bb15',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTHo4XzlXSDJfQUNGZG9XclFZZGs1Y09LQRIbQ09LRTA4MkcyX0FDRlFtb1dBb2R6RThHMFEx',
          text: 'màn hình của a bnh inch mà nhìn thích thế ạ',
          authorId: 'UCTW4sJvl4SdYYGHYmfEO32A',
          publishedAt: '2021-05-21T15:11:51.680612+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngMHIAy7yapEpb2UNmzZtUBcgHCWvi5ngGwzyIIsA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Việt Anh Hoàng',
          authorRole: '👶',
        },
        {
          _id: '60a7cdb9f2d030539874bb14',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSnl3bWRXSDJfQUNGZWtsclFZZHdESUtZQRIbQ01lRDItN18ydkFDRlVKQmhRb2RfT1lNOHc5',
          text: 'chô ông dev nghiền nhâu bay',
          authorId: 'UCXXE65MkLgUo2jWuwG4JZdQ',
          publishedAt: '2021-05-21T15:11:49.99974+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhL1PXEx1Sa7ZiXW0054iVhFOI0cl7llNSIS-NvwA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'huy trân',
          authorRole: '👶',
        },
        {
          _id: '60a7cd8bf2d030539874bb13',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDUExhaGItSDJfQUNGVVFRclFZZG9Ra09qdxIbQ1B6TXNlQ0UyX0FDRlFmYmN3RWRQNXNLMGcx',
          text: 'uống bia đi rồi làm tiếp ông dev',
          authorId: 'UCNkjfJuXM4B8x72YQcpy0WQ',
          publishedAt: '2021-05-21T15:11:03.540131+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnib9r63nIDh7MOI5cjQmW2P3AxAgVDYtoxY80dHJQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Meditation Zen Soothing',
          authorRole: '👶',
        },
        {
          _id: '60a7cd8bf2d030539874bb12',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDS1hnN2IySDJfQUNGU2dIclFZZExJa0UwdxIbQ09LRTA4MkcyX0FDRlFtb1dBb2R6RThHMFEw',
          text: 'helo a',
          authorId: 'UCTW4sJvl4SdYYGHYmfEO32A',
          publishedAt: '2021-05-21T15:11:01.050445+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngMHIAy7yapEpb2UNmzZtUBcgHCWvi5ngGwzyIIsA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Việt Anh Hoàng',
          authorRole: '👶',
        },
        {
          _id: '60a7cd6cf2d030539874bb10',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSmZIaUxHSDJfQUNGZFlJclFZZFRYOEw1ZxIbQ0xULXo2U0gyX0FDRlJybVdBb2RqYmtDb2cw',
          text: 'Hello ông dev',
          authorId: 'UCNeep7C1MoZPT6VR69Akvhw',
          publishedAt: '2021-05-21T15:10:34.226623+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhk9xCyKXh_4jqVg2jajxrxKwNZcIBebKrazQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Phạm Đình Hùng',
          authorRole: '👶',
        },
        {
          _id: '60a7cd08b02c573fe8a90d68',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSmZqc29HSDJfQUNGVVFRclFZZG9Ra09qdxIbQ01yYzMtaUcyX0FDRllkRDlRVWRSSWdOWGcw',
          text: 'chiều test live chat ổn chưa a',
          authorId: 'UCi8KhS98bLc-3Lw3oCrPmvA',
          publishedAt: '2021-05-21T15:08:54.25506+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhW5zJ1uNaEg2wSU0mumm-YJIymVtTe1N2VRtm9HXc=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Nguyễn Công Khanh',
          authorRole: '👶',
        },
        {
          _id: '60a7cc79d6e03314e05ac252',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI6ChpDSktxN3J1RzJfQUNGVVFRclFZZG9Ra09qdxIcQ0s3VnFhQ0cyX0FDRllOSGhRb2RzZzhCUnctMA',
          text: 'nhìn giống mongoose nhở',
          authorId: 'UC26CJlD2RHyLaeCO3E-tPdg',
          publishedAt: '2021-05-21T15:06:28.430136+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngcTk53kyrHg568e5yZ4XKLggB0g99wXJb_AHrTVA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thắng Phạm',
          authorRole: '👶',
        },
        {
          _id: '60a7cc69d6e03314e05ac250',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTGVLcTdTRzJfQUNGZWtsclFZZHdESUtZQRIbQ0xXZjZaaUcyX0FDRmJwUmhRb2RlM0FHekEw',
          text: 'like de',
          authorId: 'UCn_XLoIPSRDjnef3pWOq6uA',
          publishedAt: '2021-05-21T15:06:12.64828+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniEBcGhF2IQMBjX_WCJZjtJPDTBVMN3HWnHZr8XHg=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Xuân Đạt Trịnh',
          authorRole: '👶',
        },
        {
          _id: '60a7cc3fd6e03314e05ac24e',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTWlaMHFDRzJfQUNGU2dIclFZZExJa0UwdxIbQ01lRDItN18ydkFDRlVKQmhRb2RfT1lNOHc4',
          text: 'đh mua mac air m1 được ko ạ',
          authorId: 'UCXXE65MkLgUo2jWuwG4JZdQ',
          publishedAt: '2021-05-21T15:05:31.346162+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhL1PXEx1Sa7ZiXW0054iVhFOI0cl7llNSIS-NvwA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'huy trân',
          authorRole: '👶',
        },
        {
          _id: '60a7cc15d6e03314e05ac24d',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTkxsb295RzJfQUNGZG9XclFZZGs1Y09LQRIbQ0lmdnBQbUYyX0FDRlhOSmZBb2R0NTROdFEw',
          text: 'học html css lâu quá ông dev ơi , có cách nào học nhanh hơn ko ông dev',
          authorId: 'UClbeV64o32A3tAUkL7bLjgg',
          publishedAt: '2021-05-21T15:04:48.626435+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniRgzKOeHy7gUUAPWQutw5wKiPJzCz7ipS1e4dq=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'soccer-collectió',
          authorRole: '👶',
        },
        {
          _id: '60a7cc00d6e03314e05ac24c',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSmZQLW9HRzJfQUNGYVlfclFZZE9BY0dLQRIbQ05tWWpkT0UyX0FDRlFWWFdBb2R5TWNORlEw',
          text: 'e đọc đén lần thứ 3 quyển data structures and algorithm analysis mà vẫn chưa thám hết thì phải làm sao ông dev',
          authorId: 'UCTxfO0slq2KsvWjQsj6Bk-A',
          publishedAt: '2021-05-21T15:04:26.996691+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjW1zWs1CfrfMDAT8OkJW24lnrPkx5Aa8SWmA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Nhát Vu',
          authorRole: '👶',
        },
        {
          _id: '60a7cbe6d6e03314e05ac24b',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDT3YzLVBXRjJfQUNGWUFrclFZZGJrVU5LURIbQ01LMWdJUDUydkFDRmRfaWN3RWRaR0FHMGcw',
          text: 'Công ty anh còn tuyển fresher không ạ',
          authorId: 'UCEIzlFW87x9rNRRHC1GqF1g',
          publishedAt: '2021-05-21T15:04:01.803292+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjTVzqbqyvuJ5gXSVbSZvdKzEy-bsAvVfYqOSoml6M=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Minh Tien Dang',
          authorRole: '👶',
        },
        {
          _id: '60a7cbe6d6e03314e05ac24a',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSkhJaXZXRjJfQUNGVVFRclFZZG9Ra09qdxIbQ01lRDItN18ydkFDRlVKQmhRb2RfT1lNOHc3',
          text: 'đh mua mac air m1 được ko ạ',
          authorId: 'UCXXE65MkLgUo2jWuwG4JZdQ',
          publishedAt: '2021-05-21T15:03:59.994939+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhL1PXEx1Sa7ZiXW0054iVhFOI0cl7llNSIS-NvwA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'huy trân',
          authorRole: '👶',
        },
        {
          _id: '60a7cb5272749626d0975264',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDUFBUczYtRjJfQUNGU0lHNXdvZGE4Y0N4QRIbQ0pyQnMtNy0ydkFDRmNkU0tnb2RNMFVFd0Ex',
          text: 'roadmap.sh',
          authorId: 'UCLAeh5SDjUBOjnE8HTXJLGw',
          publishedAt: '2021-05-21T15:01:33.867557+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjeWisuPPm3gtioXItdBEPzbXpNfc3e2ZgyggjK2Xo=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thuan Pham',
          authorRole: '🔧',
        },
        {
          _id: '60a7cb3872749626d0975263',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTHlaaktPRjJfQUNGU0lHNXdvZGE4Y0N4QRIbQ1B6TXNlQ0UyX0FDRlFmYmN3RWRQNXNLMGcw',
          text: '😀',
          authorId: 'UCNkjfJuXM4B8x72YQcpy0WQ',
          publishedAt: '2021-05-21T15:01:08.055275+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnib9r63nIDh7MOI5cjQmW2P3AxAgVDYtoxY80dHJQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Meditation Zen Soothing',
          authorRole: '👶',
        },
        {
          _id: '60a7cb3872749626d0975261',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTTMzMzZLRjJfQUNGVVFRclFZZG9Ra09qdxIbQ01lRDItN18ydkFDRlVKQmhRb2RfT1lNOHc2',
          text: 'ông dev làm về lộ trịnh học đi ạ',
          authorId: 'UCXXE65MkLgUo2jWuwG4JZdQ',
          publishedAt: '2021-05-21T15:01:07.330038+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhL1PXEx1Sa7ZiXW0054iVhFOI0cl7llNSIS-NvwA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'huy trân',
          authorRole: '👶',
        },
        {
          _id: '60a7caca72749626d0975260',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTjZ2OGUyRTJfQUNGWHdOclFZZC1iY0w1QRIbQ0lxa2c3YUMyX0FDRllncFdBb2R3ZE1FaFEw',
          text: 'ds&a kìa bạn @@',
          authorId: 'UCcPr9sZBQZljTe9u03wCRIA',
          publishedAt: '2021-05-21T14:59:16.466694+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniUOg4HTMZZQW8WUJDLo10FscZ-h3oKN3V7XmLBKA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'FL• Olafff',
          authorRole: '🔧',
        },
        {
          _id: '60a7caa672749626d097525f',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSXZFdDkyRTJfQUNGZUFOclFZZGFpOEVZQRIbQ0k3dm9Oei0ydkFDRlJmR1dBb2RGb1FDTVEy',
          text: 'các môn học về ngành software engineering thì nên tập trung nhiều vào môn nào để chắc nền vậy ông Dev',
          authorId: 'UCebnw4OXTNad7Qh1MfY3IHw',
          publishedAt: '2021-05-21T14:58:41.964627+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniYYBeGaRTongRmCi7dVy4j1uajWkUZsuOeWQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Dũng Nguyễn',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097525e',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTXFXcGRhRDJfQUNGZmtGclFZZE1jb0dZURIbQ04zeHJxVF8ydkFDRlQzNU9BWWRnQndENnc2',
          text: 'ông dev có recomment course nào cho người mới học không ông dev',
          authorId: 'UClbeV64o32A3tAUkL7bLjgg',
          publishedAt: '2021-05-21T14:53:58.548331+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniRgzKOeHy7gUUAPWQutw5wKiPJzCz7ipS1e4dq=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'soccer-collectió',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097525d',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI6ChpDSjd6d2JPRDJfQUNGZWtsclFZZHdESUtZQRIcQ0l5Q3BxR0EyX0FDRlUwcEtnb2RTMW9HcXctMw',
          text: 'Em cam on anh',
          authorId: 'UCcI0Ku3z5QQLvByoHIvNcZg',
          publishedAt: '2021-05-21T14:52:45.618619+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh7ORBjZyIGYSJdQzZX8i82F2ElIPDpM4H9kxY_ww=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Văn Trung Phạm',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097525c',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSUM3djVTRDJfQUNGWUFrclFZZGJrVU5LURIbQ09YbnJ1R0IyX0FDRlpYQ1RBSWRtd3NHX2cx',
          text: 'anh thấy cái môi trường cho Mac có dễ hông nọ em cài cho bạn em thấy cực quá',
          authorId: 'UCiMjLie69ikuaxlcbHxWeGA',
          publishedAt: '2021-05-21T14:51:40.566951+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhghc5fEk1u7XlEX8O5vGXSZVmuiDTEZRvcUChwZA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Ngọc Tiến Trần',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097525a',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTVdMdVltRDJfQUNGWHdOclFZZC1iY0w1QRIbQ01lRDItN18ydkFDRlVKQmhRb2RfT1lNOHc1',
          text: 'em học ngu ngu em tính học cntt đh nông lâm ổn không ạ',
          authorId: 'UCXXE65MkLgUo2jWuwG4JZdQ',
          publishedAt: '2021-05-21T14:51:17.393925+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhL1PXEx1Sa7ZiXW0054iVhFOI0cl7llNSIS-NvwA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'huy trân',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975259',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDS201NWVlQzJfQUNGU2dIclFZZExJa0UwdxIbQ04zeHJxVF8ydkFDRlQzNU9BWWRnQndENnc1',
          text: 'mới học có cần nhảy thẳng vào react hay vue ko hay cần phải học javascript vậy ông dev',
          authorId: 'UClbeV64o32A3tAUkL7bLjgg',
          publishedAt: '2021-05-21T14:50:06.817498+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniRgzKOeHy7gUUAPWQutw5wKiPJzCz7ipS1e4dq=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'soccer-collectió',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975258',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSnVXeXQtQzJfQUNGU2dIclFZZExJa0UwdxIbQ0xMX2ljUDcydkFDRmNFbFdBb2RRaXNMMEEz',
          text: 'anh đang xài Vue2 hay Vue3',
          authorId: 'UCVu7fkhMLdz4unGrSMrr0gA',
          publishedAt: '2021-05-21T14:49:49.593431+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjdiFt0mmti1d0wt0D2Ff65pr_9WUiGzmoLmH5E=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Nho Hồ Công',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975257',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTWVtdE5tQzJfQUNGVVFRclFZZG9Ra09qdxIbQ002eWxNbjgydkFDRmNnd0tnb2R6N2NEcUEw',
          text: 'có ae nào học golang ko?',
          authorId: 'UC_SppENJpPrbQ504cRLarvA',
          publishedAt: '2021-05-21T14:49:36.65232+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniRyfGxPMgu3U9OXbxei_AYdx4v414jH3Gkr-L-DQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Kha Bui',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975255',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTHFaanNlQzJfQUNGZmtGclFZZE1jb0dZURIbQ0piOGxjUF8ydkFDRlZBZ0tnb2QwSGtLN1Ez',
          text: 'ủa đang làm cái gì vậy ông Dev. Làm mentor hả?',
          authorId: 'UCLLp4QBHeG9OITLG8eD5L6A',
          publishedAt: '2021-05-21T14:48:58.279138+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhQ9bo-n6PXceLLKApohDFZczX8EFMd0sHAz4I-sQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thảo Y',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975254',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI6ChpDTjd2dkwtQzJfQUNGU0lHNXdvZGE4Y0N4QRIcQ0l5Q3BxR0EyX0FDRlUwcEtnb2RTMW9HcXctMg',
          text: '4 nhân 8 luồng 1.60ghz up to 4.20ghz 6mb smart cache ram 8gb anh ạ',
          authorId: 'UCcI0Ku3z5QQLvByoHIvNcZg',
          publishedAt: '2021-05-21T14:48:42.266645+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh7ORBjZyIGYSJdQzZX8i82F2ElIPDpM4H9kxY_ww=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Văn Trung Phạm',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975253',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI6ChpDS2p1dUtPQzJfQUNGU0lHNXdvZGE4Y0N4QRIcQ0ptMnFvMkEyX0FDRlEtZVdBb2RoYW9KT3ctMQ',
          text: 'Muốn làm cho big four thì hc theo hướng dev hay se hả a tại e ít thấy tuyển dev ở mấy cty đấy',
          authorId: 'UCUcYZ3FUCR57kVZ0bmlNZwg',
          publishedAt: '2021-05-21T14:47:43.480648+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhfiyfF7PA8rn-2YHZ7tijp0GT6RczJe_JoFA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Khang Nguyen',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975252',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSW00XzR5QzJfQUNGZG9XclFZZGs1Y09LQRIbQ0pyQnMtNy0ydkFDRmNkU0tnb2RNMFVFd0Ew',
          text: '"senior font-end là làm full-stack được nhưng thích làm front-end" theo cách em nghỉ là vậy phải không ông dev?',
          authorId: 'UCLAeh5SDjUBOjnE8HTXJLGw',
          publishedAt: '2021-05-21T14:46:56.402477+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjeWisuPPm3gtioXItdBEPzbXpNfc3e2ZgyggjK2Xo=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thuan Pham',
          authorRole: '🔧',
        },
        {
          _id: '60a7c9a172749626d0975251',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDS0hPcF9lQjJfQUNGZG9XclFZZGs1Y09LQRIbQ0xMX2ljUDcydkFDRmNFbFdBb2RRaXNMMEEy',
          text: 'Nuxt của vue',
          authorId: 'UCVu7fkhMLdz4unGrSMrr0gA',
          publishedAt: '2021-05-21T14:46:10.923341+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjdiFt0mmti1d0wt0D2Ff65pr_9WUiGzmoLmH5E=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Nho Hồ Công',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975250',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTnZSenVXQjJfQUNGWUFrclFZZGJrVU5LURIbQ01fSXRxMzYydkFDRmZ4RGhRb2REX1FHUnc1',
          text: 'lý do code vue rồi không muốn quay lại react đi anh?',
          authorId: 'UCi4jkqjZH2wbi15bPcsXDjg',
          publishedAt: '2021-05-21T14:45:33.814013+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniw8sOTydT5erGd3Jfj7QcTebLv77JyHG78emAJsg=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Chiến Nguyễn Bá',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097524f',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSWphOE4tQjJfQUNGZFlJclFZZFRYOEw1ZxIbQ04zeHJxVF8ydkFDRlQzNU9BWWRnQndENnc0',
          text: 'ông dev cho hỏi học css mình có thể dùng mọi giải pháp miễn là giải quyết đúng ko ông dev',
          authorId: 'UClbeV64o32A3tAUkL7bLjgg',
          publishedAt: '2021-05-21T14:45:21.789223+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniRgzKOeHy7gUUAPWQutw5wKiPJzCz7ipS1e4dq=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'soccer-collectió',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097524e',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTnFvNk4yQjJfQUNGZG9XclFZZGs1Y09LQRIbQ1B6RXRhbUIyX0FDRlpYQ1RBSWRtd3NHX2cw',
          text: 'Giống thằng em đang search gì kìa 😺',
          authorId: 'UCAkxBMObs_LqCQX1yzJLoRQ',
          publishedAt: '2021-05-21T14:45:17.457534+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngCe8Z_6Uy07Qjk5Iuv2LUgx2dQq1j_kQ-aNlqnnA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thanh Đô Nguyễn',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097524d',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI6ChpDTS1Ldk1hQjJfQUNGYVlfclFZZE9BY0dLQRIcQ0l5Q3BxR0EyX0FDRlUwcEtnb2RTMW9HcXctMQ',
          text: 'i5 10210u em học code web có ổn khong anh',
          authorId: 'UCcI0Ku3z5QQLvByoHIvNcZg',
          publishedAt: '2021-05-21T14:44:28.498293+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh7ORBjZyIGYSJdQzZX8i82F2ElIPDpM4H9kxY_ww=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Văn Trung Phạm',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097524c',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTEdwOEllQjJfQUNGWHdOclFZZC1iY0w1QRIbQ01lRDItN18ydkFDRlVKQmhRb2RfT1lNOHcz',
          text: 'e thử anh thôi kkkkkk',
          authorId: 'UCXXE65MkLgUo2jWuwG4JZdQ',
          publishedAt: '2021-05-21T14:42:17.233632+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhL1PXEx1Sa7ZiXW0054iVhFOI0cl7llNSIS-NvwA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'huy trân',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097524b',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTkRxczRPQjJfQUNGYVlfclFZZE9BY0dLQRIbQ0xMX2ljUDcydkFDRmNFbFdBb2RRaXNMMEEx',
          text: 'Em cũng đang xài Nuxt',
          authorId: 'UCVu7fkhMLdz4unGrSMrr0gA',
          publishedAt: '2021-05-21T14:42:07.853937+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjdiFt0mmti1d0wt0D2Ff65pr_9WUiGzmoLmH5E=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Nho Hồ Công',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097524a',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTWF3bHZDQTJfQUNGU2dIclFZZExJa0UwdxIbQ015VXhyal8ydkFDRmNoRDlRVWRENEFJYVEw',
          text: 'Theo anh nên resopnsive website bằng Css hay dùng Bootstrap ạ, em là sinh viên năm 2 tìm hiểu có muộn không anh.',
          authorId: 'UCVZg_cSO55J9ofQLJUgGdwA',
          publishedAt: '2021-05-21T14:41:27.525482+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngbX0ohPTmgqQr_sGgrJLj_TMijz-XdKmjszA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Tâm Nguyễn Lê Thành',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975248',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDS2otLU9hQTJfQUNGZWtsclFZZHdESUtZQRIbQ01fSXRxMzYydkFDRmZ4RGhRb2REX1FHUnc0',
          text: '- cứ xem một ngày của web dev engineer trên mạng toàn lừa thôi anh ạ :v',
          authorId: 'UCi4jkqjZH2wbi15bPcsXDjg',
          publishedAt: '2021-05-21T14:41:08.169565+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniw8sOTydT5erGd3Jfj7QcTebLv77JyHG78emAJsg=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Chiến Nguyễn Bá',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975247',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTDZSemVhQTJfQUNGWUFrclFZZGJrVU5LURIbQ01lRDItN18ydkFDRlVKQmhRb2RfT1lNOHcy',
          text: 'ông dev nói thực tế ghê',
          authorId: 'UCXXE65MkLgUo2jWuwG4JZdQ',
          publishedAt: '2021-05-21T14:41:07.451114+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhL1PXEx1Sa7ZiXW0054iVhFOI0cl7llNSIS-NvwA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'huy trân',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975246',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI6ChpDS2lPbS1PQTJfQUNGZFlJclFZZFRYOEw1ZxIcQ0ptMnFvMkEyX0FDRlEtZVdBb2RoYW9KT3ctMA',
          text: 'Dev với se khác nhau nhiều hk a?',
          authorId: 'UCUcYZ3FUCR57kVZ0bmlNZwg',
          publishedAt: '2021-05-21T14:41:00.340043+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhfiyfF7PA8rn-2YHZ7tijp0GT6RczJe_JoFA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Khang Nguyen',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975244',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI6ChpDSmVDdDlpQTJfQUNGWUFrclFZZGJrVU5LURIcQ0l5Q3BxR0EyX0FDRlUwcEtnb2RTMW9HcXctMA',
          text: 'Hi anh',
          authorId: 'UCcI0Ku3z5QQLvByoHIvNcZg',
          publishedAt: '2021-05-21T14:40:37.7286+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh7ORBjZyIGYSJdQzZX8i82F2ElIPDpM4H9kxY_ww=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Văn Trung Phạm',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975242',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSU96dnJtQTJfQUNGWUVYZlFvZGVkd0dzURIbQ04zeHJxVF8ydkFDRlQzNU9BWWRnQndENncz',
          text: 'cho hỏi lương ông dev bao nhiêu vậy ? 😀',
          authorId: 'UClbeV64o32A3tAUkL7bLjgg',
          publishedAt: '2021-05-21T14:39:32.837809+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniRgzKOeHy7gUUAPWQutw5wKiPJzCz7ipS1e4dq=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'soccer-collectió',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975241',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDUEdkMWJhQTJfQUNGWUFrclFZZGJrVU5LURIbQ0lfZHk0M18ydkFDRlNiSWN3RWRhSWdPMFEy',
          text: 'Hello a',
          authorId: 'UCJXAM7tPyFOls-sI7B7eCzw',
          publishedAt: '2021-05-21T14:39:26.920483+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhWHq8ljWS7M1Tkg_119mnK22gUlw58StoYIg=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Huy Trương',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097523f',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSXZzX3FtQTJfQUNGWHdOclFZZC1iY0w1QRIbQ0tqV2tJRC0ydkFDRllLZVdBb2RfV2tLMGcw',
          text: 'e đang học mấy cái upload file lên cloud mà đọc document ko hiểu gì cả 😞',
          authorId: 'UCQ5_NQRyo4R-lH7UQ2ceZFA',
          publishedAt: '2021-05-21T14:39:00.33924+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhHDWWj8df4r758LZK6isYE4gk2wohbdhNNhA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Nguyễn Đình Long',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097523d',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSTJmLTZtQTJfQUNGZFlJclFZZFRYOEw1ZxIbQ0xua2w5My0ydkFDRlp0VWhRb2RaM0VHX1Ex',
          text: 'mấy job remote bên nước ngoài họ có tuyển riêng be hay fe k ạ, em lướt thấy toàn fullstack engineer ạ',
          authorId: 'UCnPi_Y2ZgOU2PDu_eSYYIRA',
          publishedAt: '2021-05-21T14:39:00.280236+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/meH2ds1u5YhJDzYg91CLkLnToVThBPll0ZtwKId4kp0tCry0IR2uU9KwUerxcnuRQHB7PR2olQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'đặng phúc',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097523c',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTk9LdzZtQTJfQUNGZFlJclFZZFRYOEw1ZxIbQ01lRDItN18ydkFDRlVKQmhRb2RfT1lNOHcx',
          text: 'chào anh sinh viên năm nhất cntt em muốn theo wed thì có ổn không ạ',
          authorId: 'UCXXE65MkLgUo2jWuwG4JZdQ',
          publishedAt: '2021-05-21T14:38:59.360116+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhL1PXEx1Sa7ZiXW0054iVhFOI0cl7llNSIS-NvwA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'huy trân',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097523b',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDUE9vbWFpQTJfQUNGZmtGclFZZE1jb0dZURIbQ0l1OWtxejkydkFDRlFsTEtnb2Rna2dHcVEy',
          text: 'stack của project này là gì v anh?',
          authorId: 'UCDjncOEzsv3UuUk24WzXYoA',
          publishedAt: '2021-05-21T14:38:56.578723+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjQxxuufvnWwXVNk3XbMo9g_y9UEz-lyV2Q_uHoZc8=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thanh Hải',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097523a',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSURCLWFXQTJfQUNGZFlJclFZZFRYOEw1ZxIbQ0pfSW00aUEyX0FDRlEzM1dBb2RIMGNJNlEw',
          text: 'chào ông 😀',
          authorId: 'UCZfdYRUVbevlIdbyv06DZbg',
          publishedAt: '2021-05-21T14:38:51.86319+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh5FS6EnzqC2YoeEJArNykJVFIetZQLpkg9LH3DFg=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Võ Mười',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975239',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSzJieVBfXzJ2QUNGZWtsclFZZHdESUtZQRIbQ0k3dm9Oei0ydkFDRlJmR1dBb2RGb1FDTVEx',
          text: 'vậy khi mà cần kiến thức sâu cho một dự án thì mình mới tìm hiểu tiếp phải không anh',
          authorId: 'UCebnw4OXTNad7Qh1MfY3IHw',
          publishedAt: '2021-05-21T14:37:31.363794+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniYYBeGaRTongRmCi7dVy4j1uajWkUZsuOeWQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Dũng Nguyễn',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975238',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSjY2Z18zXzJ2QUNGWUFrclFZZGJrVU5LURIbQ0piOGxjUF8ydkFDRlZBZ0tnb2QwSGtLN1Ex',
          text: 'Vì javascript OOP nó khác ngôn ngữ khác',
          authorId: 'UCLLp4QBHeG9OITLG8eD5L6A',
          publishedAt: '2021-05-21T14:37:26.042955+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhQ9bo-n6PXceLLKApohDFZczX8EFMd0sHAz4I-sQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thảo Y',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975237',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTkswelB6XzJ2QUNGZWtsclFZZHdESUtZQRIbQ0piOGxjUF8ydkFDRlZBZ0tnb2QwSGtLN1Ew',
          text: 'Chào ông dev, mình 25 tuổi. Mình đang tự học lập trình được khoảng 2 tháng. Có lướt tuyển dụng Front End Dev có yêu cầu OOP, thế theo ông Dev có cần cái biết OOP không?',
          authorId: 'UCLLp4QBHeG9OITLG8eD5L6A',
          publishedAt: '2021-05-21T14:37:25.141114+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhQ9bo-n6PXceLLKApohDFZczX8EFMd0sHAz4I-sQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thảo Y',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975235',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDUGVJMnZ2XzJ2QUNGZUFOclFZZGFpOEVZQRIbQ01lRDItN18ydkFDRlVKQmhRb2RfT1lNOHcw',
          text: 'Hello anh',
          authorId: 'UCXXE65MkLgUo2jWuwG4JZdQ',
          publishedAt: '2021-05-21T14:37:23.267742+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhL1PXEx1Sa7ZiXW0054iVhFOI0cl7llNSIS-NvwA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'huy trân',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975233',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTjdSME5YXzJ2QUNGZG9XclFZZGs1Y09LQRIbQ04zeHJxVF8ydkFDRlQzNU9BWWRnQndENncy',
          text: 'mở kênh hỏi đáp đi ông dev , mới học có nhiều điều cần ông dev tư vấn',
          authorId: 'UClbeV64o32A3tAUkL7bLjgg',
          publishedAt: '2021-05-21T14:36:03.421447+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniRgzKOeHy7gUUAPWQutw5wKiPJzCz7ipS1e4dq=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'soccer-collectió',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975232',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTHVqLWNyXzJ2QUNGZE1OZlFvZEw4b041dxIbQ04zeHJxVF8ydkFDRlQzNU9BWWRnQndENncx',
          text: 'sao comment nó ko hiện vậy ông dev',
          authorId: 'UClbeV64o32A3tAUkL7bLjgg',
          publishedAt: '2021-05-21T14:35:41.018603+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniRgzKOeHy7gUUAPWQutw5wKiPJzCz7ipS1e4dq=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'soccer-collectió',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975230',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTldRaklqXzJ2QUNGU0lHNXdvZGE4Y0N4QRIbQ05uUDdNdjIydkFDRmY3TFRBSWRoa1lCVFEw',
          text: 'Hello anh, project gần xong chưa ạ',
          authorId: 'UCvcYWNuyAY4gTHfhDoQXuDg',
          publishedAt: '2021-05-21T14:33:20.818298+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhl3NsUAfxpJkXMIml4uWZMtOykuX0d1qj1QYGa8Q=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Đinh Sỹ Hùng',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097522e',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSlQ3b29QXzJ2QUNGWHdOclFZZC1iY0w1QRIbQ0xua2w5My0ydkFDRlp0VWhRb2RaM0VHX1Ew',
          text: 'Làm fullstack có thực sự khó k ạ. Em thấy giỏi một mảng cũng đã khó rồi ý ạ.Thế một fullstack engineer phải thành thạo cả fe lẫn be hả a.Như vậy phải cần bao nhiêu năm KN để làm đc ở vị trí này ạ.',
          authorId: 'UCnPi_Y2ZgOU2PDu_eSYYIRA',
          publishedAt: '2021-05-21T14:33:10.706614+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/meH2ds1u5YhJDzYg91CLkLnToVThBPll0ZtwKId4kp0tCry0IR2uU9KwUerxcnuRQHB7PR2olQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'đặng phúc',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097522d',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDS1Q4Ml9uLTJ2QUNGWUVYZlFvZGVkd0dzURIbQ0k3dm9Oei0ydkFDRlJmR1dBb2RGb1FDTVEw',
          text: 'em chưa học tới nên chưa hiểu nhìu mà thấy anh stream là thích rồi',
          authorId: 'UCebnw4OXTNad7Qh1MfY3IHw',
          publishedAt: '2021-05-21T14:32:50.66914+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniYYBeGaRTongRmCi7dVy4j1uajWkUZsuOeWQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Dũng Nguyễn',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097522b',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDS3JucC1YLTJ2QUNGZmtGclFZZE1jb0dZURIbQ082XzRKajkydkFDRlVzUHR3QWRncW9DT0Ew',
          text: 'này là prj train cho các bạn à anh 😀',
          authorId: 'UCWUmFpMtwi5JI02sjp7Hqwg',
          publishedAt: '2021-05-21T14:32:07.871446+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhZK6nfqdjLlJODziSW-X_3FXFg8LxHXUyu3gvsIQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Hiền Vương Phan Thái',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975229',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTEhndE5QLTJ2QUNGWHdOclFZZC1iY0w1QRIbQ01fSXRxMzYydkFDRmZ4RGhRb2REX1FHUncz',
          text: 'nguyên nhân đây rồi :v',
          authorId: 'UCi4jkqjZH2wbi15bPcsXDjg',
          publishedAt: '2021-05-21T14:31:30.334798+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniw8sOTydT5erGd3Jfj7QcTebLv77JyHG78emAJsg=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Chiến Nguyễn Bá',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975228',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTnY3czdYLTJ2QUNGWHdOclFZZC1iY0w1QRIbQ0l1OWtxejkydkFDRlFsTEtnb2Rna2dHcVEx',
          text: 'NestJS à anh',
          authorId: 'UCDjncOEzsv3UuUk24WzXYoA',
          publishedAt: '2021-05-21T14:30:27.407351+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjQxxuufvnWwXVNk3XbMo9g_y9UEz-lyV2Q_uHoZc8=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thanh Hải',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975227',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTVRrc0pmLTJ2QUNGVVFRclFZZG9Ra09qdxIbQ0tLbDI5MzkydkFDRmN1Qndnb2RMUk1PcWcw',
          text: 'tôi không thuộc về nơi đây',
          authorId: 'UC7EMsodqu7YEb1LMkD-suWw',
          publishedAt: '2021-05-21T14:29:24.440679+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngg12NYgDqMZkWyW5u1ljCUAKhOvcrHEOm781L9=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Jason Zhang',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975225',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTXZFam9fLTJ2QUNGVVFRclFZZG9Ra09qdxIbQ01fSXRxMzYydkFDRmZ4RGhRb2REX1FHUncy',
          text: 'có khi bạn này đang làm rồi xóa project đi kéo lại lên bị',
          authorId: 'UCi4jkqjZH2wbi15bPcsXDjg',
          publishedAt: '2021-05-21T14:29:07.102318+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniw8sOTydT5erGd3Jfj7QcTebLv77JyHG78emAJsg=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Chiến Nguyễn Bá',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975224',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSS1QODR2LTJ2QUNGWUFrclFZZGJrVU5LURIbQ0xMX2ljUDcydkFDRmNFbFdBb2RRaXNMMEEw',
          text: 'git pull --rebase origin master',
          authorId: 'UCVu7fkhMLdz4unGrSMrr0gA',
          publishedAt: '2021-05-21T14:29:00.361651+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjdiFt0mmti1d0wt0D2Ff65pr_9WUiGzmoLmH5E=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Nho Hồ Công',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975222',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSWVZeG9QLTJ2QUNGYVlfclFZZE9BY0dLQRIbQ01fSXRxMzYydkFDRmZ4RGhRb2REX1FHUncx',
          text: 'thử git log của bạn này lên kiểm tra đi anh',
          authorId: 'UCi4jkqjZH2wbi15bPcsXDjg',
          publishedAt: '2021-05-21T14:28:42.848317+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniw8sOTydT5erGd3Jfj7QcTebLv77JyHG78emAJsg=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Chiến Nguyễn Bá',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975221',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI6ChpDTUR2NU83OTJ2QUNGU2dIclFZZExJa0UwdxIcQ0xEUDl1djkydkFDRldERVRBSWR5Mm9DVmctMA',
          text: 'Hè lô',
          authorId: 'UC-mjGwCm703VtpVCSyUfoiQ',
          publishedAt: '2021-05-21T14:27:59.310816+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhGxBRjpNd97wPDsDLvIyfKNnf-keLZ8s9pRw=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Nguyen Quoc Bao',
          authorRole: '🔧',
        },
        {
          _id: '60a7c9a172749626d097521f',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTmY1c2ViOTJ2QUNGWUFrclFZZGJrVU5LURIbQ0l1OWtxejkydkFDRlFsTEtnb2Rna2dHcVEw',
          text: 'git pull origin master',
          authorId: 'UCDjncOEzsv3UuUk24WzXYoA',
          publishedAt: '2021-05-21T14:27:41.699337+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjQxxuufvnWwXVNk3XbMo9g_y9UEz-lyV2Q_uHoZc8=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thanh Hải',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097521d',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSjJrbU1UODJ2QUNGVVFRclFZZG9Ra09qdxIbQ01fSXRxMzYydkFDRmZ4RGhRb2REX1FHUncw',
          text: 'push --force đi',
          authorId: 'UCi4jkqjZH2wbi15bPcsXDjg',
          publishedAt: '2021-05-21T14:22:01.540188+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniw8sOTydT5erGd3Jfj7QcTebLv77JyHG78emAJsg=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Chiến Nguyễn Bá',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097521b',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSm1SeXZqNjJ2QUNGZG9XclFZZGs1Y09LQRIbQ0ktUy1LajUydkFDRllWS1lBb2RjZE1JcXcw',
          text: 'japan lofi',
          authorId: 'UCLAeh5SDjUBOjnE8HTXJLGw',
          publishedAt: '2021-05-21T14:14:54.537915+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjeWisuPPm3gtioXItdBEPzbXpNfc3e2ZgyggjK2Xo=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thuan Pham',
          authorRole: '🔧',
        },
        {
          _id: '60a7c9a172749626d0975219',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDS2VZdzY3NjJ2QUNGWUVYZlFvZGVkd0dzURIbQ0s3ZGlvSDQydkFDRlZEY2N3RWRpOUlBZUEz',
          text: 'discord bị sao rồi',
          authorId: 'UCx6kfBTNMI50wHbL3qMetoA',
          publishedAt: '2021-05-21T14:12:19.234908+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnht73COtPsxsyizy8piyC3UoK-74DEPF6Q0paxa=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Hiếu Phan',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975218',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSVRwLXFuNjJ2QUNGWUFrclFZZGJrVU5LURIbQ0s3ZGlvSDQydkFDRlZEY2N3RWRpOUlBZUEy',
          text: 'em ns anh có nghe được không anh',
          authorId: 'UCx6kfBTNMI50wHbL3qMetoA',
          publishedAt: '2021-05-21T14:12:09.660595+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnht73COtPsxsyizy8piyC3UoK-74DEPF6Q0paxa=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Hiếu Phan',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975217',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDS1N3Nk1uNTJ2QUNGYVlfclFZZE9BY0dLQRIbQ0xUZDktSDQydkFDRmFkRTlRVWR6bHNBUXcw',
          text: 'hè lô anh :))',
          authorId: 'UCIx-3sjcqUaVzT7E9Jsw5DQ',
          publishedAt: '2021-05-21T14:08:48.031882+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngKtdmz_exB3oteV2N_tsU4sIKUfZzCwsSW0TrtSg=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Đình Thịnh Lê',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975215',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTzcxNXJYNTJ2QUNGZG9XclFZZGs1Y09LQRIbQ0oyTXVQMzQydkFDRmRSQzlRVWR2dU1McGcx',
          text: 'Chào Bro nhá :))',
          authorId: 'UCbcglEiDrVvZAP18QgWRYBw',
          publishedAt: '2021-05-21T14:08:06.064953+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjNxeh7aPi3tJbVFzRZtPGtHnSeT5l62qIIso7iEQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thành Lương',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975214',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTkNpbDZiNTJ2QUNGZG9XclFZZGs1Y09LQRIbQ1BHRC1JdjUydkFDRlZGU2hRb2RYZzRLWlEw',
          text: 'hello ông Dev, anh nhớ em ko =)))',
          authorId: 'UCSs8zf4sKpyb0lc4mhCEKLA',
          publishedAt: '2021-05-21T14:07:33.302665+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjpbrSldlOCnrH7wo61iW7qMr_AMCfF_5GlHISO=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thành Lê',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975212',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTHVKbnBiNTJ2QUNGU0lHNXdvZGE4Y0N4QRIbQ0oyTXVQMzQydkFDRmRSQzlRVWR2dU1McGcw',
          text: 'bén thía :)))',
          authorId: 'UCbcglEiDrVvZAP18QgWRYBw',
          publishedAt: '2021-05-21T14:06:59.859678+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjNxeh7aPi3tJbVFzRZtPGtHnSeT5l62qIIso7iEQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Thành Lương',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975210',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTGV2dy1YNDJ2QUNGU0lHNXdvZGE4Y0N4QRIbQ05hQzU0TDQydkFDRlJPMVdBb2RTZHdIU1Ey',
          text: 'nhưng em nghĩ k phải do focus',
          authorId: 'UCMrbYlxtYJ02tqEluWG2aqg',
          publishedAt: '2021-05-21T14:05:17.710312+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjTV1oPGFHoJ0IiBrjt6j8gJhNSaa3E8fXSWQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Hiếu Văn Nguyễn',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097520f',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDT3FwaXVINDJ2QUNGU2dIclFZZExJa0UwdxIbQ05hQzU0TDQydkFDRlJPMVdBb2RTZHdIU1Ex',
          text: 'hơi hơi anh ạ',
          authorId: 'UCMrbYlxtYJ02tqEluWG2aqg',
          publishedAt: '2021-05-21T14:05:08.38708+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjTV1oPGFHoJ0IiBrjt6j8gJhNSaa3E8fXSWQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Hiếu Văn Nguyễn',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097520e',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDT0hSazluNDJ2QUNGU2dIclFZZExJa0UwdxIbQ0tDTzRiNzQydkFDRmNkdFdBb2R2cThGU0Ex',
          text: 'hoặc cam mờ a',
          authorId: 'UCuBKIeG0i3lGceRiHytPq5Q',
          publishedAt: '2021-05-21T14:04:51.762436+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngLPd4alwZ9FujNxx4UQzdhcEVd6JpgRTHNy3zrzA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Linh ND.',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097520d',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTV9IN05qNDJ2QUNGZFlJclFZZFRYOEw1ZxIbQ1BUWmw2SDQydkFDRlVObGl3b2R5OGdIelEw',
          text: 'out',
          authorId: 'UCTxfO0slq2KsvWjQsj6Bk-A',
          publishedAt: '2021-05-21T14:04:51.122166+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjW1zWs1CfrfMDAT8OkJW24lnrPkx5Aa8SWmA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Nhát Vu',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097520c',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDSTZsemNiNDJ2QUNGWUVYZlFvZGVkd0dzURIbQ0tDTzRiNzQydkFDRmNkdFdBb2R2cThGU0Ew',
          text: 'hình như cam out nét hả a',
          authorId: 'UCuBKIeG0i3lGceRiHytPq5Q',
          publishedAt: '2021-05-21T14:04:12.861151+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngLPd4alwZ9FujNxx4UQzdhcEVd6JpgRTHNy3zrzA=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Linh ND.',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d097520a',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDT0hTa0xiNDJ2QUNGWHdOclFZZC1iY0w1QRIbQ01EbmlyXzMydkFDRmNzUktnb2RqNDhLckEw',
          text: 'ok anh',
          authorId: 'UCXCcM20r1seKCLhuDz73o7Q',
          publishedAt: '2021-05-21T14:03:38.313099+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjUYAAK-SeI2BB6z8ONwDKAyD-QnY1BCjdGFKuH4Q=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Vỹ Nguyễn Văn',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975208',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDUC1zdGEzNDJ2QUNGYVlfclFZZE9BY0dLQRIbQ0phaHA2ZjQydkFDRlJjTldBb2RVTTBLUmcw',
          text: 'hề lố a',
          authorId: 'UCBFP8-fAQkCfzt8fRBPGHpg',
          publishedAt: '2021-05-21T14:03:20.040135+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhxy6UYJPk91UktEyhYirpS_yrlpnVHEIhHGY0Q=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Nguyen Tan Anh',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975206',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTEcxdTVuNDJ2QUNGZmtGclFZZE1jb0dZURIbQ01LTzFwTDQydkFDRmN4RVlBb2RHeEVKU2cw',
          text: 'hi anh dev',
          authorId: 'UCn8TTSJAI4796uMFJjZt9TA',
          publishedAt: '2021-05-21T14:02:38.196464+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjKYRgt_InHkBwpwGGd0nX5UUMDDRgmNpqR3W-w=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Bang Nguyễn',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975204',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI6ChpDS0w0bTViNDJ2QUNGZFlJclFZZFRYOEw1ZxIcQ05TUnE0ejQydkFDRmRORTlRVWQyMDROMXctMg',
          text: 'nghe a oi',
          authorId: 'UCEIzlFW87x9rNRRHC1GqF1g',
          publishedAt: '2021-05-21T14:02:31.389267+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjTVzqbqyvuJ5gXSVbSZvdKzEy-bsAvVfYqOSoml6M=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Minh Tien Dang',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975203',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTTYyNTVYNDJ2QUNGZFlJclFZZFRYOEw1ZxIbQ0s3ZGlvSDQydkFDRlZEY2N3RWRpOUlBZUEx',
          text: 'em có nghe đây anh',
          authorId: 'UCx6kfBTNMI50wHbL3qMetoA',
          publishedAt: '2021-05-21T14:02:30.52888+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnht73COtPsxsyizy8piyC3UoK-74DEPF6Q0paxa=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Hiếu Phan',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d0975201',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDS0hGM1pYNDJ2QUNGZFlJclFZZFRYOEw1ZxIbQ0ptQnNvdjQydkFDRlhSWGhRb2RlSmdPdlEw',
          text: 'ngon lành anh ơi',
          authorId: 'UChZc2xk8wFHVeJyzw5yeZZw',
          publishedAt: '2021-05-21T14:02:30.366915+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh9FljDWSgXEo3KYqUh7CF6GdHfvTu5YTjm0Q=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Nguyễn Huy Thông',
          authorRole: '👶',
        },
        {
          _id: '60a7c9a172749626d09751ff',
          liveChatId:
            'Cg0KC2pWWHRSV09xa1pRKicKGFVDQTJ0RmsyTmR6T3pLcFNKZGYyNGNBZxILalZYdFJXT3FrWlE',
          messageId:
            'LCC.CjgKDQoLalZYdFJXT3FrWlEqJwoYVUNBMnRGazJOZHpPektwU0pkZjI0Y0FnEgtqVlh0UldPcWtaURI5ChpDTS15dTVYNDJ2QUNGWUFrclFZZGJrVU5LURIbQ05hQzU0TDQydkFDRlJPMVdBb2RTZHdIU1Ew',
          text: 'hello anh',
          authorId: 'UCMrbYlxtYJ02tqEluWG2aqg',
          publishedAt: '2021-05-21T14:02:29.807489+00:00',
          messageType: 'text',
          isResolved: false,
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjTV1oPGFHoJ0IiBrjt6j8gJhNSaa3E8fXSWQ=s88-c-k-c0x00ffffff-no-rj',
          authorName: 'Hiếu Văn Nguyễn',
          authorRole: '👶',
        },
      ],
      authors: [
        {
          _id: '60a7847a14fa8d25fcee5538',
          channelId: 'UCxQWC0JdL7eyVZrFjkXUDlg',
          name: 'Huy Hoàng Nguyễn',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhq438zJCIqGQyyzYjlPxtK52Mnivyho0oFc7lWIg=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7847a14fa8d25fcee553a',
          channelId: 'UCcPr9sZBQZljTe9u03wCRIA',
          name: 'FL• Olafff',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniUOg4HTMZZQW8WUJDLo10FscZ-h3oKN3V7XmLBKA=s88-c-k-c0x00ffffff-no-rj',
          role: '🔧',
        },
        {
          _id: '60a7855d14fa8d25fcee553e',
          channelId: 'UCWl402K3V7s0eCmicXKBIGQ',
          name: 'LAVAxLộc',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh_Ss7GipxW41M5fflBZBteEz-0nRgmGq5cSpwd=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7858614fa8d25fcee5541',
          channelId: 'UCA2tFk2NdzOzKpSJdf24cAg',
          name: 'Ông Dev',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniUCEs24rFdyoW2EMl0p6M-PtQfAJfMIHqW1bXr=s88-c-k-c0x00ffffff-no-rj',
          role: '👑',
        },
        {
          _id: '60a7878a14fa8d25fcee5548',
          channelId: 'UCImi_dDogA_-l4CFbmNfFDA',
          name: 'Bóng đá Tổng hợp',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh0fC5HunaBcAhC8GZz3xYLpimrC8Ck93jlqg=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a787b514fa8d25fcee554a',
          channelId: 'UCkNbkZOQRc0sw_mrQpRXxuA',
          name: 'Xuân Trọng',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwng8WVvGwLH3D_5FTDsXOsdYVA7Xut6g5AtJEOjB6-4=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a787e814fa8d25fcee554e',
          channelId: 'UCTxfO0slq2KsvWjQsj6Bk-A',
          name: 'Nhát Vu',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjW1zWs1CfrfMDAT8OkJW24lnrPkx5Aa8SWmA=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a787f214fa8d25fcee5551',
          channelId: 'UC4x8HMTRFDSYYWNf-8lztPg',
          name: 'DDRUM',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjwVKlUlusinb0tu3L9hWDZ8TEagvidmxryE0JC1w=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a787f814fa8d25fcee5553',
          channelId: 'UCEIzlFW87x9rNRRHC1GqF1g',
          name: 'Minh Tien Dang',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjTVzqbqyvuJ5gXSVbSZvdKzEy-bsAvVfYqOSoml6M=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a787fd14fa8d25fcee5555',
          channelId: 'UCnPi_Y2ZgOU2PDu_eSYYIRA',
          name: 'đặng phúc',
          avatarUrl:
            'https://yt3.ggpht.com/meH2ds1u5YhJDzYg91CLkLnToVThBPll0ZtwKId4kp0tCry0IR2uU9KwUerxcnuRQHB7PR2olQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7880214fa8d25fcee5557',
          channelId: 'UCnMXjLi64Dy9kKiAohJnK8w',
          name: 'Vương Toàn Thắng',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhg5ApXJN2euoMaA0ivn8S8hWMu_asG_Z_sHfaHXQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7882714fa8d25fcee555a',
          channelId: 'UCzS50dTNt_zl-Xn4yWMs3sg',
          name: 'Thành Đạt Nguyễn',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnia63F3ZrpX-UmYshUxePUcTmITEySY0bpnVwc2=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a788649b4c4a5f1c40394f',
          channelId: 'UCAmvEph7jZlshQJccddVByA',
          name: 'Hùng Lê Kim',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnj34471WZW-J0DAT9GyGkjPojVRd4GB6KKo2n-Aiw=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a788a49b4c4a5f1c403953',
          channelId: 'UCgH3jKJMu-P-y-q3uaEZpRA',
          name: 'Lực Đình',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngNkoPFDVvHGkTBfyQafU7u0ki49juqRtepVfYs=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a788c99b4c4a5f1c403955',
          channelId: 'UCn17XwH0VMEuKz-2YFlKfDA',
          name: 'Doanh Maple',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjTUEjlDg9JoRc9dgTmn7NeifXhQ08vZtOVraDhSZE=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a789029b4c4a5f1c403957',
          channelId: 'UCYZ-3Ytof24IuRHzXXKBiOw',
          name: 'Lâm Nguyễn',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjY5IMMUZBRsj04NR1sMXgUYwz_ISMS4U31PjpU=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78977c9d14037a4f55b52',
          channelId: 'UC-agGoanKxRobN4FGANx0TA',
          name: 'Hùng Nguyễn Huy',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniqXSm8RkfyUek5OD5araqgckpXbtF7-WZLvQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78986c9d14037a4f55b56',
          channelId: 'UC97j3idXeaAd51mRIhPbOqw',
          name: 'Thanh Sơn Lê',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhgYpNr9ZwXDBnIthcry3KUaoKpd0_G806LCw=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78d28c9d14037a4f55b71',
          channelId: 'UCewekSv7CYAlYEUn8hSwPgQ',
          name: 'Minh Vũ Nguyễn',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhOsuP5jq4Loj7N7bfOMWYj9AmIui3uNOoF_g=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78d28c9d14037a4f55b73',
          channelId: 'UCAkxBMObs_LqCQX1yzJLoRQ',
          name: 'Thanh Đô Nguyễn',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngCe8Z_6Uy07Qjk5Iuv2LUgx2dQq1j_kQ-aNlqnnA=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78d28c9d14037a4f55b75',
          channelId: 'UCi8KhS98bLc-3Lw3oCrPmvA',
          name: 'Nguyễn Công Khanh',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhW5zJ1uNaEg2wSU0mumm-YJIymVtTe1N2VRtm9HXc=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78d28c9d14037a4f55b77',
          channelId: 'UCeDH09YS9dbjMS4NFjD7YTg',
          name: 'Tín Lý',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjNgeQokVF6blRmw5okuBwIQwSavfr4sDzu-g=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78d28c9d14037a4f55b79',
          channelId: 'UCZfdYRUVbevlIdbyv06DZbg',
          name: 'Võ Mười',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh5FS6EnzqC2YoeEJArNykJVFIetZQLpkg9LH3DFg=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78d28c9d14037a4f55b7b',
          channelId: 'UCrc8Jv4p8-Cn0wl58HL3Z-g',
          name: 'Tấn Nguyễn',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwng8U33CIeLDf4Ky6lwSRDS4qjG-1pL-Z6HqAPP5=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78d28c9d14037a4f55b7d',
          channelId: 'UC6gICJmGyAJFfr93jUmq7zw',
          name: 'Hiếu Lưu',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjzlfC9RnNk1UyXIl1AAXqzqEaqvQrI2pTGCTUB=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78d28c9d14037a4f55b80',
          channelId: 'UCOlDLao9rgoVprKQoVJLIvg',
          name: 'vua tay đôi',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngTBCyXPM6D6E6SR4ShRnq-7ix8aK1npNFF4g=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78d28c9d14037a4f55b84',
          channelId: 'UCfXunfVQRoUran9b2p3tRjg',
          name: 'tmn',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhawcBYefISYZ-9knp-dfTMk_WB6xpZv_aGekA-fQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78d28c9d14037a4f55b89',
          channelId: 'UCADkVqlkZNtMA-9H3Aq2dQw',
          name: 'devzxje fake',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngbbyHrC6yW6cjTw2Wv2bT4U7ra_8dFSCT5I_UhnA=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78d28c9d14037a4f55b8b',
          channelId: 'UCn7a_z2jgLIIynVwdvT_iMQ',
          name: 'Tín Trần Trung',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhvxZ7ud-fgCF2kUjrfrZhIv2puYeZE-SmQQVtGKg=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78da2c9d14037a4f55b8d',
          channelId: 'UCIMk1xn7OtfvlGe8CIrqWSA',
          name: 'Ngoc Nguyen',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjs1mDsC7DBSd2o0k7cGdmfbvgygXrp64bUnA=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78ea572a4d86d5859dd0a',
          channelId: 'UCQIe3VUwfMAfwSKLka9V0jw',
          name: 'Hùng Quốc',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnha5O0rPxHb2Qu_B3sZDr2hs9mMufthianVMM1u=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78f12e52b4f65545e7112',
          channelId: 'UCSmFAjikcgSbdq1twJ5DaLw',
          name: 'Hector Luong',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngG1KrYjV-im_QZwl762kYCJEc-aI9WUEbaDjlouk0=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a78f28e52b4f65545e7117',
          channelId: 'UCB6u_CraScGwgc72mgW-hyw',
          name: 'Thành Long Ngô',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwng2KRmxdyPrTSvsY9DvLw2RnSZxozSHIOCc9jd-Cg=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d09751fe',
          channelId: 'UCMrbYlxtYJ02tqEluWG2aqg',
          name: 'Hiếu Văn Nguyễn',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjTV1oPGFHoJ0IiBrjt6j8gJhNSaa3E8fXSWQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975200',
          channelId: 'UChZc2xk8wFHVeJyzw5yeZZw',
          name: 'Nguyễn Huy Thông',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh9FljDWSgXEo3KYqUh7CF6GdHfvTu5YTjm0Q=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975202',
          channelId: 'UCx6kfBTNMI50wHbL3qMetoA',
          name: 'Hiếu Phan',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnht73COtPsxsyizy8piyC3UoK-74DEPF6Q0paxa=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975205',
          channelId: 'UCn8TTSJAI4796uMFJjZt9TA',
          name: 'Bang Nguyễn',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjKYRgt_InHkBwpwGGd0nX5UUMDDRgmNpqR3W-w=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975207',
          channelId: 'UCBFP8-fAQkCfzt8fRBPGHpg',
          name: 'Nguyen Tan Anh',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhxy6UYJPk91UktEyhYirpS_yrlpnVHEIhHGY0Q=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975209',
          channelId: 'UCXCcM20r1seKCLhuDz73o7Q',
          name: 'Vỹ Nguyễn Văn',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjUYAAK-SeI2BB6z8ONwDKAyD-QnY1BCjdGFKuH4Q=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d097520b',
          channelId: 'UCuBKIeG0i3lGceRiHytPq5Q',
          name: 'Linh ND.',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngLPd4alwZ9FujNxx4UQzdhcEVd6JpgRTHNy3zrzA=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975211',
          channelId: 'UCbcglEiDrVvZAP18QgWRYBw',
          name: 'Thành Lương',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjNxeh7aPi3tJbVFzRZtPGtHnSeT5l62qIIso7iEQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975213',
          channelId: 'UCSs8zf4sKpyb0lc4mhCEKLA',
          name: 'Thành Lê',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjpbrSldlOCnrH7wo61iW7qMr_AMCfF_5GlHISO=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975216',
          channelId: 'UCIx-3sjcqUaVzT7E9Jsw5DQ',
          name: 'Đình Thịnh Lê',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngKtdmz_exB3oteV2N_tsU4sIKUfZzCwsSW0TrtSg=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d097521a',
          channelId: 'UCLAeh5SDjUBOjnE8HTXJLGw',
          name: 'Thuan Pham',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjeWisuPPm3gtioXItdBEPzbXpNfc3e2ZgyggjK2Xo=s88-c-k-c0x00ffffff-no-rj',
          role: '🔧',
        },
        {
          _id: '60a7c9a172749626d097521c',
          channelId: 'UCi4jkqjZH2wbi15bPcsXDjg',
          name: 'Chiến Nguyễn Bá',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniw8sOTydT5erGd3Jfj7QcTebLv77JyHG78emAJsg=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d097521e',
          channelId: 'UCDjncOEzsv3UuUk24WzXYoA',
          name: 'Thanh Hải',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjQxxuufvnWwXVNk3XbMo9g_y9UEz-lyV2Q_uHoZc8=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975220',
          channelId: 'UC-mjGwCm703VtpVCSyUfoiQ',
          name: 'Nguyen Quoc Bao',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhGxBRjpNd97wPDsDLvIyfKNnf-keLZ8s9pRw=s88-c-k-c0x00ffffff-no-rj',
          role: '🔧',
        },
        {
          _id: '60a7c9a172749626d0975223',
          channelId: 'UCVu7fkhMLdz4unGrSMrr0gA',
          name: 'Nho Hồ Công',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjdiFt0mmti1d0wt0D2Ff65pr_9WUiGzmoLmH5E=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975226',
          channelId: 'UC7EMsodqu7YEb1LMkD-suWw',
          name: 'Jason Zhang',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngg12NYgDqMZkWyW5u1ljCUAKhOvcrHEOm781L9=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d097522a',
          channelId: 'UCWUmFpMtwi5JI02sjp7Hqwg',
          name: 'Hiền Vương Phan Thái',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhZK6nfqdjLlJODziSW-X_3FXFg8LxHXUyu3gvsIQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d097522c',
          channelId: 'UCebnw4OXTNad7Qh1MfY3IHw',
          name: 'Dũng Nguyễn',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniYYBeGaRTongRmCi7dVy4j1uajWkUZsuOeWQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d097522f',
          channelId: 'UCvcYWNuyAY4gTHfhDoQXuDg',
          name: 'Đinh Sỹ Hùng',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhl3NsUAfxpJkXMIml4uWZMtOykuX0d1qj1QYGa8Q=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975231',
          channelId: 'UClbeV64o32A3tAUkL7bLjgg',
          name: 'soccer-collectió',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniRgzKOeHy7gUUAPWQutw5wKiPJzCz7ipS1e4dq=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975234',
          channelId: 'UCXXE65MkLgUo2jWuwG4JZdQ',
          name: 'huy trân',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhL1PXEx1Sa7ZiXW0054iVhFOI0cl7llNSIS-NvwA=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975236',
          channelId: 'UCLLp4QBHeG9OITLG8eD5L6A',
          name: 'Thảo Y',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhQ9bo-n6PXceLLKApohDFZczX8EFMd0sHAz4I-sQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d097523e',
          channelId: 'UCQ5_NQRyo4R-lH7UQ2ceZFA',
          name: 'Nguyễn Đình Long',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhHDWWj8df4r758LZK6isYE4gk2wohbdhNNhA=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975240',
          channelId: 'UCJXAM7tPyFOls-sI7B7eCzw',
          name: 'Huy Trương',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhWHq8ljWS7M1Tkg_119mnK22gUlw58StoYIg=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975243',
          channelId: 'UCcI0Ku3z5QQLvByoHIvNcZg',
          name: 'Văn Trung Phạm',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh7ORBjZyIGYSJdQzZX8i82F2ElIPDpM4H9kxY_ww=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975245',
          channelId: 'UCUcYZ3FUCR57kVZ0bmlNZwg',
          name: 'Khang Nguyen',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhfiyfF7PA8rn-2YHZ7tijp0GT6RczJe_JoFA=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975249',
          channelId: 'UCVZg_cSO55J9ofQLJUgGdwA',
          name: 'Tâm Nguyễn Lê Thành',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngbX0ohPTmgqQr_sGgrJLj_TMijz-XdKmjszA=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d0975256',
          channelId: 'UC_SppENJpPrbQ504cRLarvA',
          name: 'Kha Bui',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniRyfGxPMgu3U9OXbxei_AYdx4v414jH3Gkr-L-DQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7c9a172749626d097525b',
          channelId: 'UCiMjLie69ikuaxlcbHxWeGA',
          name: 'Ngọc Tiến Trần',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhghc5fEk1u7XlEX8O5vGXSZVmuiDTEZRvcUChwZA=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7cb3872749626d0975262',
          channelId: 'UCNkjfJuXM4B8x72YQcpy0WQ',
          name: 'Meditation Zen Soothing',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnib9r63nIDh7MOI5cjQmW2P3AxAgVDYtoxY80dHJQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7cc69d6e03314e05ac24f',
          channelId: 'UCn_XLoIPSRDjnef3pWOq6uA',
          name: 'Xuân Đạt Trịnh',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwniEBcGhF2IQMBjX_WCJZjtJPDTBVMN3HWnHZr8XHg=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7cc79d6e03314e05ac251',
          channelId: 'UC26CJlD2RHyLaeCO3E-tPdg',
          name: 'Thắng Phạm',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngcTk53kyrHg568e5yZ4XKLggB0g99wXJb_AHrTVA=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7cd6cf2d030539874bb0f',
          channelId: 'UCNeep7C1MoZPT6VR69Akvhw',
          name: 'Phạm Đình Hùng',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhk9xCyKXh_4jqVg2jajxrxKwNZcIBebKrazQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7cd8bf2d030539874bb11',
          channelId: 'UCTW4sJvl4SdYYGHYmfEO32A',
          name: 'Việt Anh Hoàng',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwngMHIAy7yapEpb2UNmzZtUBcgHCWvi5ngGwzyIIsA=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7ce22f2d030539874bb17',
          channelId: 'UCkaTWNz-O4MDV6OzZqt7MJQ',
          name: 'Đỉnh Tiểu',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh2ErRNzB-HAAVnVd8XM4Zg-riUYwkUKGpCTG_guQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7cf5cf2d030539874bb28',
          channelId: 'UCdxahxK0f7OVofmWVQHf0Aw',
          name: 'Văn Thử Nguyễn',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwni6KCwNpA_5SRH9WcaqatgH43DG7MY8C3pZ7A=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7cf6cf2d030539874bb2b',
          channelId: 'UCOkMGmtjw6-oTweKEB9Ll2g',
          name: 'Nhã Nguyễn',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhu5SPig7qTr9C_3Sm-QSACP8OITXnU57TZxw=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7cf7cf2d030539874bb2e',
          channelId: 'UCJDMX31jsUomae5GuSO-1sg',
          name: 'Công Nam Lê',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnjxykSC5iADe6vU1-EpYW9feQQ0FHTbS1rrzQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7d1d1f2d030539874bb32',
          channelId: 'UCMLBzrtcoRqV5nxo46wy-Mg',
          name: 'Vũ Bảo Phúc',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnh41hkVuloEz5Xlv0wX1GhzmF5omq0bbjvWtGHMZg=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7d6d3ba8b833cdcde5140',
          channelId: 'UC80IZHeivsaZyB2TuvZk-_w',
          name: 'Kiet Tuan',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwng0X76VSSWEcBHE5--n8NVYwj3YdaZJJnYYhadF=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7d786ba8b833cdcde5142',
          channelId: 'UCi742f1D24kyihZZCuT07VA',
          name: 'Bummm Kim zj',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhqN8p3axsTcLoXbYKh7IwNmuslpiGoBx7FrQ=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
        {
          _id: '60a7da23ba8b833cdcde5144',
          channelId: 'UCClOqkmKvLwD756KLr78qBQ',
          name: 'Chau Dang',
          avatarUrl:
            'https://yt3.ggpht.com/ytc/AAUvwnhMgwhcevDdQ4G-s90vW6cG96-T8OwAreuJFYeGow=s88-c-k-c0x00ffffff-no-rj',
          role: '👶',
        },
      ],
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
      const res = await this.$axios.get(
        `http://localhost:3458/api/v1/live-chat/messages/${messageId}/archive`
      )
      if (!res.data) {
        this.messages[messageIndex].isArchived = false
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
  --author-name-color: #FFF1DC;
  --message-text-color: rgba(255, 255, 255, 0.9);;
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
