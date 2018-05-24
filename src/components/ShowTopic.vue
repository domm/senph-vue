<template>
  <div>
    <h2>{{ topic.url }}</h2>
    <ul>
      <ShowComment
        v-for="c in topic.comments"
        :comment="c"
        :key="c.ident"
      />
    </ul>
  </div>
</template>

<script>
import ShowComment from './ShowComment.vue'
export default {
  name: 'ShowTopic',
  components: {
    ShowComment
  },
  props: [
    'topic'
  ]
}
</script>

