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
      <h2 class="SectionHeading">Projects</h2>
      <button
        class="filterButt"
        :class="{ buttSelected: isSelected('All') }"
        @click="updateSelected('All')"
      >
        All
      </button>
      <button
        class="filterButt"
        v-for="tag in $page.filteredTags.edges"
        :key="tag.id"
        :class="{ buttSelected: isSelected(tag.node.Name) }"
        @click="updateSelected(tag.node.Name)"
      >
        {{ tag.node.Name }}
      </button>

      <div class="cards projectsInner">
        <Project
          v-for="edge in $page.projects.edges"
          :key="edge.node.id"
          v-bind="edge.node"
        ></Project>
      </div>
    </section>

    <section class="contactMe">
      <h2>Contact Me</h2>
      <p class="contactText">
        Send me a email at
        <a class="contactText" href="mailto:timmcgilly@gmail.com">
          timmcgilly@gmail.com</a
        >
      </p>
    </section>

    <section>
      <p class="centered">
        Copyright &copy; {{ new Date().getFullYear() }} Tim McGilly
      </p>
    </section>
  </Layout>
</template>

<script>
import Project from "~/components/Project.vue";
export default {
  data: function () {
    return {
      selectedFilter: "All",
    };
  },
  metaInfo: {
    title: "Hello, world!",
  },
  components: {
    Project,
  },
  methods: {
    isSelected(filterName) {
      return this.selectedFilter === filterName;
    },
    updateSelected(filterName) {
      this.selectedFilter = filterName;
    }
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
        tags{
          id
          Name
        }
      }
    }
  }
  filteredTags: allStrapiTag(sortBy: "Name", order: ASC, filter: {FilterTag: {eq: true}}){
 		edges{
      node{
        id
        Name
        FilterTag
      }
    }   
  }
}
</page-query>

<style lang="scss">
$section-padding-hor: 15vw;

section {
  padding-left: $section-padding-hor;
  padding-right: $section-padding-hor;
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

/* Text */
.subtitle {
  font-weight: 400;
  font-size: 43px;
  margin: 10px;
}

.SectionHeading {
  font-size: 42px;
}

.fa-3x {
  padding-right: 0.1em;
  padding-left: 0.1em;
}

.centered {
  text-align: center;
}

/*Filter Buttons */
.filterButt {
  background-color: #ffffff;
  color: black;
  border: none;
  padding: 10px 15px;
  margin: 10px;
  font-family: "Source Sans Pro", sans-serif;
  font-weight: 600;
  font-size: 19px;
  outline: none;
  width: max-content;
}

.filterButt:hover {
  background-color: #ebebeb;
  cursor: pointer;
}

.buttSelected {
  background-color: #d8d8d8;
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
    flex: 0 1 calc(50% - (#{$section-padding-hor} / 2));
  }
}

@media screen and (min-width: 60em) {
  .card {
    // flex: 0 1 #{ 33vw - $section-padding-hor /3};
    flex: 0 1 calc(25%);
  }
}

/* Projects */
.projects {
  background-color: #f2f2f2;
  padding-bottom: 75px;
}
section > h2 {
  padding-bottom: 10px;
  margin: 0;
  padding-top: 35px;
  display: inline-block;
}

/* Contact me */
.contactMe {
  padding-bottom: 30px;
}

.contactText {
  font-size: 25px;
}
</style>
