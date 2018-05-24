<template>
  <li>
    <div class="from"><span class="user-name">{{ comment.user_name }}</span> wrote on <span class="created">{{ comment.created }}</span></div>
    <div class="comment" v-html="comment.body"></div>
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

