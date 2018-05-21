<template>
  <li>
    <h4>{{ comment.username }} {{ comment.created }}</h4>
    <p>{{ comment.body }}</p>
    <ul>
      <ShowComment
        v-for="reply in comment.comments"
        :comment="reply"
        :key="reply.ident"
      />
    </ul>
  </li>
</template>

<script>
export default {
  name: 'ShowComment',
  props: [
    'comment'
  ]
}
</script>

