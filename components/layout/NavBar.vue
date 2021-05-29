<template>
  <div>
    <b-navbar type="dark" variant="dark">
      <b-navbar-nav class="container justify-content-start">
        <li
          class="nav-item"
          v-for="(page, index) in menuItems.edges"
          :key="index"
          @click="activo = !activo"
          :class="{
            'b-nav-dropdown': page.node.childItems.nodes.length > 0,
            dropdown: page.node.childItems.nodes.length > 0,
            show: activo
          }"
        >
          <b-link
            :to="page['node'].path"
            class="nav-link text-light"
            :class="{
              'dropdown-toggle': page.node.childItems.nodes.length > 0
            }"
            >{{ page["node"].label }}
            <ul
              class="dropdown-menu dropdown-menu-right"
              v-if="page.node.childItems.nodes.length > 0"
              :class="{ show: activo }"
            >
              <li v-for="hijo in page.node.childItems.nodes" :key="hijo.id">
                <nuxt-link class="dropdown-item" :to="hijo.path"
                  >{{ hijo.label }}
                </nuxt-link>
              </li>
            </ul>
          </b-link>
        </li>
      </b-navbar-nav>
    </b-navbar>
  </div>
</template>

<script>
import menuItems from "~/queries/menu/menu";
export default {
  data() {
    return {
      activo: false
    };
  },
  apollo: {
    menuItems: {
      query: menuItems,
      prefetch: true
    }
  },
  methods: {
    toggleActive() {}
  }
};
</script>

<style lang="scss" scoped></style>
