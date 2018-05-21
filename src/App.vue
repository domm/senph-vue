<template>
  <div id="app">
    <ul>
      <ShowComment :comment="test"/>
    </ul>
  </div>
</template>

<script>
import ShowComment from './components/ShowComment.vue'

export default {
  name: 'app',
  components: {
    ShowComment
  },
  data: function () { return {
    test: {
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
    }
  }
  }
}
</script>


