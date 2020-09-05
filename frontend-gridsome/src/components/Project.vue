<template>
  <div class="card projectCard">
    <h3>{{Title}}</h3>
    <p>{{ShortDescription}}</p>
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
}

.projectCard{
    padding: 10px;
}
</style>