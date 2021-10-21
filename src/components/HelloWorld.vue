<template>
  <div>
    <table>
      <tr><th>ランキング</th><td>{{recipe_rank}}</td></tr>
      <tr><th>タイトル</th><td>{{recipe_title}}</td></tr>
      <tr><img :src="recipe_image" alt=""></tr>
      <tr><li v-for="recipe in recipe_materials" :key="recipe.id">{{recipe}}</li></tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data:() => ({
    recipe_rank:"",
    recipe_title:"",
    recipe_image:"",
    recipe_materials:"",
  }),
  props:{
    recipe_data:Object,

  },
  mounted(){
    this.recipe_rank = this.recipe_data.rank
    this.recipe_title = this.recipe_data.recipeTitle
    this.recipe_image = this.recipe_data.smallImageUrl
    this.recipe_materials = this.recipe_data.recipeMaterial


  }
}
</script>

<style scoped>

</style>
