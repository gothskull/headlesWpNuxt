<template>
  <b-container class="mt-5">
    <h1 class="text-center">{{ post.title }}</h1>
    <p v-html="post.excerpt"></p>
  </b-container>
</template>

<script>
export default {
  computed: {
    post() {
      return {
        title: "Titulo delPost",
        slug: "Slug del Post",
        content: "<p>Contenido del Post</p>",
        excerpt: "<p>Excerpt del Post</p>"
      };
    }
  }
};
</script>

<style lang="scss" scoped></style>
