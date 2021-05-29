<template>
  <article>
    <b-card class="mb-2 shadow" :title="post.title">
      <b-card-text v-html="post.excerpt"></b-card-text>
      <b-button
        variant="success"
        size="sm"
        :to="{ name: 'slug', params: { slug: post.slug } }"
        >VER MÁS</b-button
      >
    </b-card>
  </article>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      reqired: true
    }
  }
};
</script>

<style lang="scss" scoped></style>
