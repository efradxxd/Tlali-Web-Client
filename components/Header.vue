 <template>
 
 <div>
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
</div>
</template>


  <style scoped>
#hr1 {
  height: 10px;
  margin-left: 450px;
  background-color:red;
  border: none;
  /* height: 10px; */
  width: 60%;
  
}
#txti{
color: midnightblue;
  margin-left: 450px;
/* padding: 15px; */
/* margin: 50px; */
font-size: 27px;
align-content: center;
font-weight: bold;
}

.imagenes{
  margin-left: 1220px;
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