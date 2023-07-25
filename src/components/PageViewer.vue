<template>
  <div class="container">
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
  props: {
    page: {
      type: Object,
      default(rawProps) {
        return {
          pageTitle: "",
          content: "",
        };
      },
    },
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
