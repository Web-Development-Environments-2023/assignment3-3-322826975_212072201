<template>
  <div class="container">
    <row>
    <RecipePreviewList v-if="$root.store.username"
      title="Favorite Recipes"
      :is_random="false"
      :is_favorite="true"
      :is_my_created="false"
      :is_my_family="false"
      :class="{
        row: true,
        RandomRecipes: true,
        blur: !$root.store.username,
        center: true
      }"
      disabled
    ></RecipePreviewList>
    </row>
  </div>
</template>

<script>
import RecipePreviewList from "../components/RecipePreviewList";
export default {
  components: {
    RecipePreviewList,
    
  }
};
</script>

<style lang="scss" scoped>
.RandomRecipes {
  margin: 10px 0 10px;
  position: absolute;
  display: inline-block;
}
.blur {
  -webkit-filter: blur(5px); /* Safari 6.0 - 9.0 */
  filter: blur(2px);
}
.row{
  justify-items:flex-end;
}
::v-deep .blur .recipe-preview {
  pointer-events: none;
  cursor: default;
}
</style>
