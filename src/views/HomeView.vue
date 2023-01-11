<template>
  <div class="home">
    <h1>All Heroes</h1>
    <section class="box">
      <card-heroe v-for="dado in dados" :key="dado.id" :heroName="dado.name" :heroImg="dado.images.lg"></card-heroe>
    </section>
  </div>
</template>

<script setup>
  import {ref, onMounted} from 'vue'
  
  // @ is an alias to /src
  import CardHeroe from '@/components/CardHeroe.vue';

  const dados = ref([])
  
  async function getHeroes(){
    const req = await fetch('https://cdn.jsdelivr.net/gh/akabab/superhero-api@0.3.0/api/all.json')
    const data = await req.json()
    dados.value = Object.assign({}, data);
    console.log(dados.value)
  }

  onMounted(() => {
    getHeroes()
  })
</script>

<style lang="scss">
  h1{
    color: red;
  }
  .box{
    display: grid;
    grid-template-columns: repeat(4,1fr);
  }
</style>