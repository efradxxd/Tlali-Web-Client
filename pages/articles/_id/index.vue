
<template>

  <section class="single-article">
        <script src="https://unpkg.com/vue"></script>
<script src="https://unpkg.com/vue-resize-text"></script>

       <p id="txti">Tlali</p>
        <div  class="imagenes" >
         <img  src="@/assets/fb.png" class="imgfb">
         <img src="@/assets/twi.jpg" class="imgtwi">
        </div>
      <hr id="hr1">
      <br>
      <br>
    
        <br>
    <form>
      
      
      <h2>ID:</h2>
      <p> {{articlesData.ID}}</p>
      
      <h2>Título:</h2>
      <p> {{articlesData.ARTICLE.Title}}</p>
     
      <h2>Autor:</h2>
      <p> {{articlesData.ARTICLE.Author}}</p>
      <p> {{articlesData.IMG.Author}}</p>
      
      <h2>Fecha:</h2>
      <p> {{articlesData.ARTICLE.DT}}</p>
      <p> {{articlesData.IMG.DT}}</p>
     
      <h2>Localización</h2>
      <p> {{articlesData.ARTICLE.Location}}</p>
      <p> {{articlesData.IMG.Location}}</p>
      
      <h2>Estado de publicación:</h2>
      <p> {{articlesData.ARTICLE.PublishStatus}}</p>
      
      <h2>Sección:</h2>
      <p> {{articlesData.ARTICLE.Section}}</p>
      
      <h2>Etiquetas:</h2>
      <p> {{articlesData.ARTICLE.Tags}}</p>
      
      <h2>Contenido:</h2>
      <p> {{articlesData.ARTICLE.Content}}</p>
      
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
        ID:               document.getElementById("id").value,
        ARTICLE: {
          Author:         document.getElementById("author").value,
          Content:        document.getElementById("content").value,
          DT:             document.getElementById("date").value,
          Location:       document.getElementById("location").value,
          PublishStatus:  document.getElementById("status").value,
          Section:        document.getElementById("section").value,
          Tags:           document.getElementById("tags").value,
          Title:          document.getElementById("title").value
        },
        IMG: {
          Author: "Test Author",
          DT: "Date Test",
          Location: "Location Test",
          S3DIR: "Test dir"
        }
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
  margin: 20px;
  align-self: auto;
  width: auto;
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
  
  width: 30;
  height: 30px; 
}

/* input,
textarea {
  box-sizing: border-box;
  border: 1px solid #cccccc;
  padding: 5px;
  margin: 5px;
  width: 500px;
  margin-block-start: 2px;
  margin-block-end: 2px;
} */

</style>
