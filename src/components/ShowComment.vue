<template>
  <li class="senph-comment">
    <div class="senph-comment-from"><span class="senph-comment-username">{{ comment.user_name }}</span> wrote on <span class="senph-comment-created">{{ comment.created }}</span></div>
    <div class="senph-comment-body" v-html="comment.body"></div>
    <ul class="senph-replies">
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

