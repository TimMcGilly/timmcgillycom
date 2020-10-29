<template>
  <div class="card projectCard">
    <h3>{{ Title }}</h3>
    <div class="cardBody">
    <p class="projectDescription">{{ ShortDescription }}</p>
    <button id="learnButton">Learn More</button>
    </div>
    <hr />
    <div class="tagSection">
      <button class="tag" v-for="tag in Tags" :key="tag.id">
        {{ tag.Name }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {},
  props: ["Title", "ShortDescription", "Tags"],
};
</script>

<style scoped>
h3 {
  font-size: 33px;
  font-weight: 700;
  margin: 10px 0px 10px 0px;
}

.projectCard {
  margin: 10px;
  padding: 5px 25px 5px 25px;
  background-color: white;
  display: flex;
  flex-direction: column;
}

.projectDescription {
  font-size: 21px;
  margin-bottom: 10px;
}

.cardBody {
  flex-grow: 1;
}

hr {
  margin: 0px;
}

#learnButton {
  background-color: #dedede;
  color: black;
  border: none;
  padding: 10px 15px;
  margin-bottom: 20px;
  font-family: "Source Sans Pro", sans-serif;
  font-weight: 600;
  font-size: 19px;
  outline: none;
  width: max-content;
}

#learnButton:hover {
  background-color: #ebebeb;
  cursor: pointer;
}

.tagSection {
  margin: 10px 0px;
}

.tag {
  background-color: Transparent;
  border: none;
  cursor: pointer;
  outline: none;
}
</style>