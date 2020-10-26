<template>
  <ul>
    <li >
      <img :src="gambar">
      <p>
        {{index+1}}. nama : {{hero.nama}}
      </p>
      <p>
        type : {{hero.type}}
      </p>
    </li>
  </ul>
</template>


<script>
  export default {
    props: ['hero', 'index'],
    computed: {
      gambar () {
        return require("../assets/hero/hero/"+this.hero.gambar);

      }
    }
  }
  </script>


  <style scoped>
    p {
      color: blue;
      margin: 0;
    }
    img {
      width: 80px;
      border: 2px solid #222e31;
    }
    li {
      list-style: none;
    }
  </style>