<script src="https://unpkg.com/vue"></script>
<script src="https://unpkg.com/vue-resize-text"></script>
<template>
   <section class="articles">
    <!-- <img src="@/assets/menu.png" class="imgmenu"> -->
    <p id="txti">Tlali</p>
    <div  class="imagenes" >
    <img  src="@/assets/fb.png" class="imgfb">
    <img src="@/assets/twi.jpg" class="imgtwi">
    </div>
  <hr id="hr1">
  <br>
  <br>
    <!-- Render and <Article/> component for each article fetched from articlesData -->
    <Article
      v-for="article in articlesData"
      v-bind:key="article.ID"
      v-bind:id="article.ID"
      v-bind:author="article.ARTICLE.Author"
      v-bind:title="article.ARTICLE.Title"
    />
  </section>

</template>

<script>
import Article from "@/components/Article"; //Get the Article component

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
  margin-left: 400px;
  width: 50%;
}
#hr1 {
  height: 10px;
  margin: 0 20px;
  background-color:red;
  border: none;
  /* height: 10px; */
  width: 100%;
  
}
#txti{
color: midnightblue;
padding: 15px;
margin: 20px;
font-size: 27px;
align-content: center;
font-weight: bold;
}

.imagenes{
  margin-left: 750px;
  display: flex;
}

.imgfb{
  width: 18;
  height: 30px;
}

.imgtwi{
  width: 25;
  height: 30px; 
}
</style>
