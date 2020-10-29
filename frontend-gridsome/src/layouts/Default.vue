<template>
  <div class="layout">
    <header class="header">
    </header>

    <slot />
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
import NavBar from "~/components/NavBar.vue";

export default {
  components: {
    NavBar
  }
};
</script>


<style>
@import url("https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@400;600;700&display=swap");

body {
  margin: 0px;
}

h1,
h2,
h3,
h4,
p,
a,
input {
  font-family: "Source Sans Pro", sans-serif;
  color: #444444;
}

h1 {
  font-size: 59px;
}

h2 {
  font-size: 43px;
}

a {
  font-size: 21px;
  font-weight: 600;
}

</style>
