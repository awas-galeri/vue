<template>
  <div class="container">
    <div class="row">
      <div class="col-lg-12">
        <h1>{{ page.pageTitle }}</h1>
        <p>{{ page.content }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["page"],
};
</script>
