<template>
  <div id="senph">
    <ShowTopic :topicUrl="topicUrl" />
  </div>
</template>

<script>

import Vue from 'vue'
import axios from 'axios'
import VueAxios from 'vue-axios'

Vue.use(VueAxios, axios);
Vue.config.productionTip = false

import ShowTopic from './components/ShowTopic.vue'

var App = Vue.extend({
  name: 'Senph',
  components: {
    ShowTopic
  },
  data: function () { return {
    topicUrl: '',
  }},
  beforeMount() {
    this.topicUrl = this.$el.dataset.topicUrl;
  },
});

export default App;

</script>

