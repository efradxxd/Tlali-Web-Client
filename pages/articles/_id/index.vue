
<template>

  <section class="single-article">
        <script src="https://unpkg.com/vue"></script>
<script src="https://unpkg.com/vue-resize-text"></script>

    <form>
      
      
      <h2>ID:</h2>
      <p> {{articlesData.id}}</p>
      
      <h2>Título:</h2>
      <p> {{articlesData.article.title}}</p>
     
      <h2>Autor:</h2>
      <p> {{articlesData.author}}</p>
      <p> {{articlesData.s3Dir}}</p>
      
      <h2>Fecha:</h2>
      <p> {{articlesData.dt}}</p>
      <p> {{articlesData.s3Dir}}</p>
     
      <h2>Localización</h2>
      <p> {{articlesData.location}}</p>
      <p> {{articlesData.s3Dir}}</p>
      
      <h2>Estado de publicación:</h2>
      <p> {{articlesData.publishStatus}}</p>
      
      <h2>Sección:</h2>
      <p> {{articlesData.article.section}}</p>
      
      <h2>Etiquetas:</h2>
      <p> {{articlesData.article.tags}}</p>
      
      <h2>Contenido:</h2>
      <p> {{articlesData.article.content}}</p>
      
      <br>
    </form>
  </section>
</template>

<script>
export default {
  created: function() {
    console.log("Page loaded");
  },

  methods: {
    updateInfo: function() { //Called by the button
      console.log("Button clicked, processing data...");
      console.log(this.buildJSON());
      this.postData(this.buildJSON()); //Call POST
    },

    async postData(articleJSON) {
      console.log(this.$route.params.id);
      this.$axios.$put('https://o2dstvq9sb.execute-api.us-west-2.amazonaws.com/dev/articles/' + this.$route.params.id,
      articleJSON).then(function (response) {
        console.log(response);
      })
      .catch(function (error) {
        console.log(error);
      });
    },

//Build an object with the data from the form, return it as articleData
    buildJSON: function() {
      var articleData = {
        id:             document.getElementById("id").value,
        dt:             document.getElementById("date").value,
        author:         document.getElementById("author").value,
        location:       document.getElementById("location").value,
        publishStatus:  document.getElementById("status").value,
        s3Dir: "Test dir",
        
        article: {
          content:        document.getElementById("content").value,    
          section:        document.getElementById("section").value,
          tags:           document.getElementById("tags").value,
          title:          document.getElementById("title").value,
        },

      };
      return articleData;
    }
  },

  async asyncData({ $axios, params }) { //Fetch the data from a single article, given the ID
    const url =
      "https://o2dstvq9sb.execute-api.us-west-2.amazonaws.com/dev/articles/" +
      params.id;
    console.log(url);
    const articlesData = await $axios.$get(url);
    console.log("Data fechted");
    return { articlesData };
  }
};
</script>

<style scoped>
/* #submit {
  background-color: rgb(230, 230, 230);
} */

h1 {
  text-align: center;
  font-size: 30px;
}

h2 {
  color: black;
  font-weight: bold;
  font-size: 14px;
  margin-block-start: 2px;
  margin-block-end: 2px;
}

form {
  
  box-sizing: border-box;
  text-align: center;
  border: 2px solid slategray;
  /* margin: 20px; */
  align-self: auto;
   margin-left: 180px;
  width: 100%;
  font-family: 'Lucida Sans';
  color: grey;


}
.single-article{
    padding: 30px;
  display: flex;
  flex-flow: row wrap;
  margin-left: 400px;
  width: 50%;
}

</style>
