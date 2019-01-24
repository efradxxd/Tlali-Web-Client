<template>
<!-- Navigation bar -->
  <header>
    <nav class="borde">
      <ul>
        
        <p id="txti">Menú</p>
        <hr id="hr1">
        <br>
        <li><nuxt-link class="changecolor" to="/">Inicio</nuxt-link></li>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/">Local</nuxt-link></li>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/">Nacional</nuxt-link></li>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/">Internacional</nuxt-link></li>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/">Editoriales</nuxt-link></li>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/">Seguridad</nuxt-link></li>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/">Tecnología</nuxt-link></li>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/">Sociales</nuxt-link></li>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/">Deportes</nuxt-link></li>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/">Finanzas</nuxt-link></li>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/">Lo que te interesa</nuxt-link></li>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/">Redes sociales</nuxt-link></li>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/">Mis noticias</nuxt-link></li>
        
        <br>
        <hr id="hr2">

        <p id="txti">Publicaciones Recientes</p>
        <hr id="hr1">
        <br>
        <li><nuxt-link class="changecolor" to="/"></nuxt-link></li>
        <br>
        <br>
        <br>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/"></nuxt-link></li>
        <br>
        <br>
        <br>
        <hr id="hr2">
        <li><nuxt-link class="changecolor" to="/"></nuxt-link></li>
        <br>
        <br>
        <br>
        <hr id="hr2">


      </ul>
    </nav>
 
  </header>
  
  <!-- <p id="txti">Client Viewer</p> -->
</template>

<style>
body {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  margin: 0;
}

a {
  color:black;
  text-decoration: none;
}


header {
  background-color:ghostwhite;
  font-size: 20px;
  font-family: fantasy;
  width: 400px;
  height: auto;
  position: absolute;
  justify-content: center;
  align-items: center;
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
  /* display: flex; */
  justify-content: center;
  align-items: center;
}
.changecolor:hover{
  color: brown;
  transition: .5s;
  /* background-color: blue; */
}

li {
  margin: 0 20px;
  padding: 3%;
  font-family: 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  
}
#txti{

color: black;
padding: 15px;
margin: 20px;
font-size: 27px;
align-content: center;
font-weight: bold;
}

#hr1 {
  height: 2px;
  margin: 0 20px;
  background-color: red;
  border: none;
  /* height: 10px; */
  width: 40%;
  
}
 #hr2 {
   margin: 0 20px; 
  border: .5px solid lightgrey;
  width: 80%;
  
} 
.imgmenu{
  
    margin-left: 10px;
    display: flex;
    width: 40;
    height: 40px;
}
.borde{
  border-color: brown;
}

</style>



