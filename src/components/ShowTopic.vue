<template>
  <div class="senph-topic">
    <ul v-if="topic.comments.length > 0">
      <ShowComment
        v-for="c in topic.comments"
        :comment="c"
        :key="c.ident"
      />
    </ul>
    <div v-else class="senph-no-comments">
      No comments yet.
    </div>
  </div>
</template>

<script>
import ShowComment from './ShowComment.vue';


export default {
  name: 'ShowTopic',
  components: {
    ShowComment
  },
  props: [
    'topicUrl'
  ],
  created: function(){
    this.fetchItems();
  },
  methods: {
    fetchItems(){
      if (this.topicUrl) {
        this.axios.get(this.topicUrl).then((response) => {
          this.topic = response.data;
        });
      }
    }
  },
  data: function () { return {
    topic: {
      comments: []
    }
  }}
}
</script>

