<template>
  <div id="app">
    <ShowTopic :topicUrl="topicUrl" />
  </div>
</template>

<script>
import ShowTopic from './components/ShowTopic.vue'

export default {
  name: 'app',
  components: {
    ShowTopic
  },
  data: function () { return {
    topicUrl: 'http://localhost:6006/api/comment/https%3A%2F%2Fdomm.plix.at%2Fperl%2F2017_08_things_i_learned_at_european_perl_conference_2018_amsterdam.html',
  }},
  created: function() {
    const configElement = document.getElementById( 'senph-config' );
    if (configElement === null) { return }
    const config = JSON.parse( configElement.innerHTML );
    if (config.topicUrl) {
    this.topicUrl = config.topicUrl;
    }
  }
}
</script>


