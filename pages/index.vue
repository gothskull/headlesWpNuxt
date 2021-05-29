<template>
  <b-container class="mt-5">
    <h1 class="text-center">Headless Wordpress y Nuxt</h1>
    <b-row class="justify-content-center">
      <b-col cols="8" class="mt-5">
        <Postcard v-for="post in posts" :key="post.slug" :post="post" />
        <div class="fles w-100">
          <div class="ml-auto">
            <nuxt-link :to="{ query: { after: pageInfo.endCursor } }">
              <span>Próxima Página</span></nuxt-link
            >
          </div>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  computed: {
    posts() {
      return [
        {
          title: "Titulo delPost",
          slug: "Slug del Post",
          content: "<p>Contenido del Post</p>",
          excerpt: "<p>Excerpt del Post</p>"
        },
        {
          title: "Titulo delPost",
          slug: "Slug del Post",
          content: "<p>Contenido del Post</p>",
          excerpt: "<p>Excerpt del Post</p>"
        }
      ];
    },
    pageInfo() {
      return {
        endCursor: "",
        hasNextPage: false,
        hasPreviousPage: false,
        startCurswor: ""
      };
    }
  }
};
</script>

<style lang="scss" scoped></style>
