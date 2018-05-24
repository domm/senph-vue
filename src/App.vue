<template>
  <div id="senph">
    <ShowTopic :topicUrl="topicUrl" />
  </div>
</template>

<script>
import ShowTopic from './components/ShowTopic.vue'

export default {
  name: 'Senph',
  components: {
    ShowTopic
  },
  data: function () { return {
    topicUrl: '',
  }},
  created: function() {
    const configElement = document.getElementById( 'senph-config' );
    if (configElement === null) {
      return
    }
    const config = JSON.parse( configElement.innerHTML );
    if (config.topicUrl) {
      this.topicUrl = config.topicUrl;
    }
  }
}
</script>

