<template>
  <div>
    <table>
      <tr><th>ランキング</th><td>{{rank_data}}</td></tr>
      <tr><th>タイトル</th><td>{{title_data}}</td></tr>
      <tr><img :src="recipe_image" alt=""></tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data:() => ({
    // recipe_rank:"aa",
    // recipe_title:"",
    // recipe_image:"",
    // recipe_material:"",
    // recipe:"",
  }),
  props:{
    data:Object,
    rank_data:String,
    title_data:String,
    recipe_image:String,
  },
  mounted(){
    // const first_recipe = recipe_data
    // this.recipe_title = first_recipe.recipeTitle
    // this.recipe_image = first_recipe.smallImageUrl
    // this.recipe_material = first_recipe.mediumMaterial
    // this.recipe_rank = first_recipe.rank


  }
}
</script>

<style scoped>

</style>
