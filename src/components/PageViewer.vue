<template>
  <div v-if="page" class="container">
    <div class="row">
      <div class="col-lg-12">
        <h1 class="emphasize">{{ page.pageTitle }}</h1>
        <p>
          This is the <span class="emphasizes">{{ page.content }}</span>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  created() {
    this.page = this.$pages.getSinglePage(this.$route.params.index);
  },
  data() {
    return {
      page: null,
    };
  },
};
</script>
<style scoped>
.emphasize {
  color: darkblue;
}
.emphasizes {
  color: darkblue;
  font-weight: 600 !important;
}
</style>
