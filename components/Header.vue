<template>
<section>
<!-- Navigation bar -->
  <header>
    <nav>
      <ul>
        <li><nuxt-link to="/">Inicio</nuxt-link></li>

      </ul>
    </nav>
  </header>
  <p id="txti">Client Viewer</p>
 
 </section>
  
</template>



<style>
body {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  margin: 0;
}

a {
  color:whitesmoke;
  text-decoration: none;
}

header {
  background-color: teal;
  font-size: 45px;
  font-family: fantasy;
  width: 100%;
  height: 120px;
  display: flex;
  justify-content: center;
  align-items: center;
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

li {
  margin: 0 10px;
}
#txti{
color: firebrick;
padding: 15px;
margin: 20px;
font-size: 25px;
align-content: center;

}
</style>


