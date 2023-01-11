<template>
  <section class="card">
    <img :src="heroImg" :alt="heroName">
    <div>
      <h3>{{heroName}}</h3>
    </div>
  </section>
</template>

<script>
  export default {
    name: 'CardHero',
    data(){
      return{}
    },
    props:{
      heroImg: String,
      heroName: String,
    }
  }
</script>

<style lang="scss" scoped>
  .card{
    box-shadow: 0 1px 2px #ccc;
    border: 1px solid #ccc;
    border-radius: 8px;
    width: max-content;
    padding: .625rem;

    h3{
      text-align: center;

    }
  }
</style>