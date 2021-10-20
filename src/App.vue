<template>
<HelloWorld v-for="data in datas.result" 
  :key="data.id" 
  :rank_data="data.rank" 
  :title_data="data.recipeTitle"
  :recipe_image="data.smallImageUrl"
  
/>


</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data:() =>({
    datas:"",
  }),
  async mounted(){
    const url = "https://app.rakuten.co.jp/services/api/Recipe/CategoryRanking/20170426?format=json&applicationId=1098499049918798561"

    const response = await fetch(url);
    this.datas = await response.json();

    
  },
}
</script>

<style>

</style>
