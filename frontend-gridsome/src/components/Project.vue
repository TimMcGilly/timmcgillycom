<template>
  <div class="card projectCard">
    <h3>{{ Title }}</h3>
    <p class="projectDescription">{{ ShortDescription }}</p>
    <button id="learnButton">Learn More</button>
    <hr/>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {},
  props: ["Title", "ShortDescription"],
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
}

.projectDescription {
  font-size: 21px;
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
}

#learnButton:hover {
  background-color: #ebebeb;
  cursor: pointer;
}
</style>