<template>
  <div>
    <div class="nav-container">
      <div v-on:click="toggleNav" class="nav-toggle" id="js-navbar-toggle">
        <div class="bar"></div>
        <div class="bar"></div>
        <div class="bar"></div>
      </div>
      <nav v-bind:class="{ active: navVisable }" class="nav-list" id="nav-list">
        <li class="nav-item">
          <a class="nav-link" href="/">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/#projects">Projects</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/#contact">Contact</a>
        </li>
      </nav>
    </div>
    <hr />
  </div>
</template>

<script>
export default {
  data() {
    return {
      navVisable: false
    };
  },
  methods: {
    toggleNav: function() {
      this.navVisable = !this.navVisable;
    }
  }
};
</script>

<style scoped>
.nav-container {
  max-width: 1300px;
  margin: 0 auto;
}
.nav-list {
  /* margin: 1rem 0rem 1.5rem auto;*/
  margin-top: 1rem;
  margin-bottom: 1.5rem;
  margin-left: auto;
  margin-right: 0rem;
  flex-direction: column;
  text-align: center;
  /*justify-content: flex-end;*/

  display: none;
}
.nav-item {
  margin: 1rem 0 0 0;
  list-style: none;
}

a {
  font-weight: 400;
  font-size: 28px;
  text-decoration: none;
  background: transparent;
  color: black;
}

hr {
  border: none;
  height: 1px;
  /* Set the hr color */
  color: #333; /* old IE */
  background-color: #333;
  margin: 0px;
  padding: 0px;
}

.nav-toggle {
  margin: 2rem 2rem 2rem auto;
  width: 35px;
  cursor: pointer;
}

.active {
  display: flex;
}

.bar {
  width: 35px;
  height: 5px;
  background-color: black;
  margin: 6px 0;
}

@media screen and (min-width: 768px) {
  .nav-list {
    display: flex;
    flex-direction: row;
  }

  .nav-item {
    margin: 1rem 1.5rem 0 2.5rem;
  }

  .nav-toggle {
    display: none;
  }
}
</style>
