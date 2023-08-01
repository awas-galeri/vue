<template>
  <li>
    <a
      class="nav-link"
      :class="activeClasses"
      :href="page.link.url"
      :title="`This link goes to the ${page.link.text} page`"
      @click.prevent="$bus.$emit('navbarLinkActived', index)"
      >{{ page.link.text }}</a
    >
  </li>
</template>

<script>
export default {
  props: ["page", "index", "isActive"],
  computed: {
    activeClasses() {
      return {
        active: this.isActive,
        emphasize: this.isActive,
      };
    },
  },
};
</script>
<style scoped>
.emphasize {
  font-weight: 600 !important;
}
</style>
