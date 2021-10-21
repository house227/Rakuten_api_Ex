<template>
  <div>
    <table class="table table-bordered" >
      <tr><th  class="spot">ランキング：</th><td>{{recipe_rank}}</td></tr>
      <tr><th>タイトル：</th><td>{{recipe_title}}</td></tr>
      <tr><td colspan="2"><img :src="recipe_image" alt="" class="image"></td></tr>
      <tr>
        <th class="recipe_list">材料：</th>
          <td class="recipe_list">
            <ul>
              <li v-for="recipe in recipe_materials" :key="recipe.id" >{{recipe}}</li>
            </ul>
          </td>
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
    recipe_materials:"",
  }),
  props:{
    recipe_data:Object,

  },
  mounted(){
    this.recipe_rank = this.recipe_data.rank
    this.recipe_title = this.recipe_data.recipeTitle
    this.recipe_image = this.recipe_data.mediumImageUrl
    this.recipe_materials = this.recipe_data.recipeMaterial


  }
}
</script>

<style scoped>
table{
  margin-bottom: 100px;
}

th{
  width: 18%;
  height: 80%;
  font-size: 25px;
  
}
td{
  font-size: 25px;
}
.image{
  padding: 0 0 0 130px;
  width: 45%;
}

.recipe_list{
  height: 5%;
}
ul{
  font-size: 22px;
  display: flex;
	flex-wrap: wrap;
  margin: auto;
  padding: auto;

}
li{
  margin-right: 15px;
  list-style: none;
}

</style>
