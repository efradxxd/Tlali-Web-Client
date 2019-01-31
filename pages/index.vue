<script src="https://unpkg.com/vue"></script>
<script src="https://unpkg.com/vue-resize-text"></script>
<template>

  <v-container fluid>
    <div class="lista">
<ul class="submenu">
  <li>SECCION</li>
  <li><a href="default.asp">Local</a></li>
  <li><a href="news.asp">Nacional</a></li>
  <li><a href="contact.asp">Internacional</a></li>
  <li><a href="about.asp">Columnas</a></li>
</ul>
    </div>
    <!-- <img src="@/assets/menu.png" class="imgmenu"> -->
   
    <!-- Render and <Article/> component for each article fetched from articlesData -->
    <Article
      v-for="article in articlesData"
      v-bind:key="article.id"
      v-bind:id="article.id"
      v-bind:author="article.author"
      v-bind:title="article.article.title"
    />
  <v-layout row wrap>
      <v-flex grow wrap>  
  <v-card 
      v-for="article in articlesData"
      :key="article"
        class="mx-auto"
      color="#26c6da"
      dark
      max-width="400"
    >
      <v-card-title>
        <v-icon
          large
          left
        >
          mdi-twitter
        </v-icon>
        <span class="title font-weight-light">{{article.article.section}}</span>
      </v-card-title>
  
      <v-card-text class="headline font-weight-bold">
{{article.article.title}}
      </v-card-text>
                  <v-card-text>{{article.article.content.slice(0, 70) }}...</v-card-text>

      <v-card-actions>
        <v-list-tile class="grow">
          <v-list-tile-avatar color="grey darken-3">
            <v-img
              class="elevation-6"
              src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light"
            ></v-img>
          </v-list-tile-avatar>
  
          <v-list-tile-content>
            <v-list-tile-title>Autor</v-list-tile-title>
          </v-list-tile-content>
  
          <v-layout
            align-center
            justify-end
          >
            <v-icon class="mr-1">mdi-heart</v-icon>
            <span class="mr-1">·</span>
            <v-icon class="mr-1">mdi-share-variant</v-icon>
            <span class="subheading">EN PORTADA</span>
          </v-layout>
        </v-list-tile>
      </v-card-actions>
    </v-card>  
    </v-flex>  
   </v-layout>
  </v-container>
</template>

<script>

import Article from "@/components/Article"; //Get the Article component


//Comentario de prueba 2
//Comentario 4
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
.submenu {
    display: flex;
  list-style-type: none;
  margin: 0;
  padding: 0;
}
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
