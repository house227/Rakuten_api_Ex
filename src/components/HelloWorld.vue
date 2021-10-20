<template>
  <div>
    <table>
      <tr>
        <th>ランキング</th> <td>{{recipe_rank}}</td>
      </tr>
      <tr>
        <th>タイトル</th><td>{{recipe_title}}</td>
      </tr>
      <tr>
        <th>イメージ</th><td><img :src="recipe_image" alt="" ></td>
      </tr>
      <tr>
        <th>必要食材</th><td v-for="recipe in recipe_material" :key="recipe">{{recipe}}</td>
      </tr>
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
    recipe_material:"",
    recipe:"",
  }),
  async mounted(){
    const url = "https://app.rakuten.co.jp/services/api/Recipe/CategoryRanking/20170426?format=json&applicationId=1098499049918798561"

    const response = await fetch(url);
    const data = await response.json();
    
    for(let i = 0; i < 3; i++){

    }

    const first_recipe = data.result[1]
    this.recipe_title = first_recipe.recipeTitle
    this.recipe_image = first_recipe.smallImageUrl
    this.recipe_material = first_recipe.mediumMaterial
    this.recipe_rank = first_recipe.rank

  }
}
</script>

<style scoped>

</style>
