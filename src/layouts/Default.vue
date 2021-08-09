<template>
  <div>
    <div class="layout">
      <header class="header">
        <strong>
          <!-- <g-link to="/">{{ $static.metadata.siteName }}</g-link> -->
        </strong>
        <nav class="nav">
          <!-- <g-link class="nav__link" to="/">Home</g-link> -->
          <!-- <g-link class="nav__link" to="/about/">About</g-link> -->
        </nav>
      </header>
      <slot />
    </div>
    <Footer />
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
import Footer from "~/components/Footer";

export default {
  components: {
    Footer
  }
};
</script>

<style>
html {
  font-size: 14px;
}

@media (min-width: 768px) {
  html {
    font-size: 16px;
  }
}

body {
  font-family: "Helvetica Neue", Arial, "Hiragino Kaku Gothic ProN", "Hiragino Sans", Meiryo, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
  background-color: #d5e4dc;
}

.layout {
  max-width: 760px;
  margin: 0 auto;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
}
</style>
