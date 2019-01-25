<script src="https://unpkg.com/vue"></script>
<script src="https://unpkg.com/vue-resize-text"></script>
<template>
   <section class="articles">
    <!-- <img src="@/assets/menu.png" class="imgmenu"> -->
   
    <!-- Render and <Article/> component for each article fetched from articlesData -->
    <Article
      v-for="article in articlesData"
      v-bind:key="article.id"
      v-bind:id="article.id"
      v-bind:author="article.author"
      v-bind:title="article.article.title"
    />
  </section>

</template>

<script>
import Article from "@/components/Article"; //Get the Article component
//Comentario de prueba 2
export default {
  components: {
    Article //Declare components to use in this document/page
  },

// Fetch articles from API and return object as articlesData,
// ready to be used on <template>

  async asyncData({ $axios }) {
    const articlesData = await $axios.$get(
      "https://o2dstvq9sb.execute-api.us-west-2.amazonaws.com/dev/articles"
    );
    return { articlesData };
  }
};
</script>

<style scoped>
.articles {
  padding: 30px;
  display: block;
  flex-flow: row wrap;
  /* margin-left: 400px; */
  width: 50%;
  align-self: auto;
   margin-left: 500px;
}

</style>
