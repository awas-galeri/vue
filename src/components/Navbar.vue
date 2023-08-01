<template>
  <nav
    :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar', 'navbar-expand-lg']"
  >
    <div class="container">
      <a class="navbar-brand" href="#">Vue Learn</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <navbar-link
            v-for="(page, index) in publishedPages"
            class="nav-item"
            :key="index"
            :page="page"
            :index="index"
          ></navbar-link>

          <li>
            <router-link
              :to="`/pages/create`"
              class="nav-link"
              active-class="active"
              >Create Page</router-link
            >
          </li>
        </ul>
      </div>
      <form class="d-flex">
        <button class="btn btn-dark" @click.prevent="changeTheme()">
          Theme
        </button>
      </form>
    </div>
  </nav>
</template>

<script>
import NavbarLink from "./NavbarLink.vue";

export default {
  components: {
    NavbarLink,
  },
  created() {
    this.getThemeSetting();

    this.pages = this.$pages.getAllPages();
  },
  computed: {
    publishedPages() {
      return this.pages.filter((p) => p.published);
    },
  },
  data() {
    return {
      theme: "dark",
      pages: [],
    };
  },
  methods: {
    changeTheme() {
      let theme = "light";

      if (this.theme == "light") {
        theme = "dark";
      }
      this.theme = theme;
      this.storeThemeSetting();
    },
    storeThemeSetting() {
      localStorage.setItem("theme", this.theme);
    },
    getThemeSetting() {
      let theme = localStorage.getItem("theme");

      if (theme) {
        this.theme = theme;
      }
    },
  },
};
</script>
