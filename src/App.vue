<template>
  <navbar
    :pages="pages"
    :active-page="activePage"
    :nav-link-click="(index) => (activePage = index)"
  ></navbar>
  <page-viewer :page="pages[activePage]"></page-viewer>
</template>

<script>
import PageViewer from "./components/PageViewer.vue";
import Navbar from "./components/Navbar.vue";

export default {
  components: {
    Navbar,
    PageViewer,
  },
  data() {
    return {
      activePage: 0,
      pages: [
        {
          link: { text: "Home", url: "index.html" },
          pageTitle: "Home Page",
          content: "home content",
        },
        {
          link: { text: "About", url: "about.html" },
          pageTitle: "About Page",
          content: "about content",
        },
        {
          link: { text: "Contact", url: "contact.html" },
          pageTitle: "Contact Page",
          content: "contact content",
        },
      ],
    };
  },
};
</script>
