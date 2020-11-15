<template>
  <div>
    <h1 v-html="$page.project.Title" />
    <div v-html="$page.project.ShortDescription" />
    <div v-html="$page.project.LongDescription" />
    <vue-simple-markdown :source="$page.project.LongDescription"></vue-simple-markdown>
  </div>
</template>

<page-query>
query ($id: ID!) {
  project: strapiProject(id: $id) {
    Title
    ShortDescription
    LongDescription
  }
}
</page-query>