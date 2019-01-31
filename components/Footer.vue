<template>
<div>

  </div>
</template>


<script>
export default {
      data: () => ({
      icons: [
        'fa fa-facebook',
        'fab fa-twitter',
        'fab fa-google-plus',
        'fab fa-linkedin',
        'fab fa-instagram'
      ]
    })
};
</script>

<style scoped>
a {
  color: #000000;
  text-decoration: none;
}

h1 {
  font-size: 20px;
  margin-block-start: 5px;
  margin-block-end: 5px;
}

h2 {
  font-size: 12px;
  margin-block-end: 5px;
  margin-block-end: 5px;
}

.article {
  text-align: center;
  border: 1px solid #cccccc;
  margin: 10px auto 10px auto;
  width: 70%;
}

.article:hover {
background-color: rgb(204, 241, 255);
}

</style>
