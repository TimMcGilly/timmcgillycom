<template>
  <Layout>
    <section class="heroBackground intro">
      <h1>Hi, I'm Tim McGilly</h1>
      <p class="subtitle">Student and Hobbyist Software Developer</p>
      <i class="fab fa-github fa-3x"></i>
      <i class="fab fa-linkedin fa-3x"></i>
      <i class="fas fa-envelope fa-3x"></i>
    </section>

    <section class="projects">
      <a id="projects" class="anchor"></a>
      <h2>Projects</h2>
      <div class="cards projectsInner">
        <Project v-for="edge in $page.projects.edges" :key="edge.node.id" v-bind="edge.node"></Project>
      </div>
    </section>
  </Layout>
</template>

<script>
import Project from "~/components/Project.vue";
export default {
  metaInfo: {
    title: "Hello, world!",
  },
  components: {
    Project,
  },
};
</script>

<page-query>
query {
  projects: allStrapiProject {
    edges {
      node {
        id
        Title
        ShortDescription
      }
    }
  }
}
</page-query>

<style>
section {
  padding-left: 5vw;
  padding-right: 5vw;
}

/* Background */
.intro::after {
  backdrop-filter: blur(10px);
  content: "";
  width: 100%;
  height: 100%;
}

.intro {
  text-align: center;
  padding-top: 25vh;
  padding-bottom: 30vh;
}

.heroBackground {
  background-image: url("../assets/MountainsHero.jpg");
  background-size: auto;
  background-position: center;
}

.intro > h1,
p {
  margin: 10px;
}

/* Text */
.subtitle {
  font-weight: 400;
  font-size: 43px;
}

.fa-3x {
  padding-right: 0.1em;
  padding-left: 0.1em;
}

/* Cards */
.cards {
  display: flex;
  flex-wrap: wrap;
}

@media screen and (min-width: 40em) {
  .cards {
    display: flex;
    flex-wrap: wrap;
  }

  .card {
    flex: 0 1 calc(50% - 2em);
  }
}

@media screen and (min-width: 60em) {
  .card {
    flex: 0 1 calc(33% - 2em);
  }
}

/* Projects */
.projects {
  margin-left: 5vw;
  margin-right: 5vw;
}
.projects>h2{
  margin-bottom: 10px;
}

.projectsInner {
  margin-left: 2.5vw;
  margin-right: 2.5vw;
}
</style>
