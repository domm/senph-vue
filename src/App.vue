<template>
  <div id="app">
    <ShowTopic :topic="topic"/>
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
    topic: {
      url:"http://test",
      comments: [{
        ident:"1",
        username:"top",
        created:"1",
        body:"start",
        comments:[
          { ident:"2", username: "aa", created: "123", body: "test", comments: [] },
          { ident:"3", username: "bb", created: "44", body: "hase", comments: [
            { ident:"4", username: "aa", created: "5", body: "reply", comments: [] } ,
            { ident:"5", username: "aa2", created: "6", body: "reply2", comments: [
              { ident:"6", username: "x", created: "9", body: "re-reply", comments: [] }
            ] }
          ] },
          { ident:"7", username: "zz", created: "123", body: "zz", comments: [] },
        ]
      }]
    }
  }
  }
}
</script>


