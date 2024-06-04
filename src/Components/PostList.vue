<template>
  <div v-if="posts.length > 0"><h3>Список постов</h3></div>
  <h2 style="color: red; text-align: center; margin-top: 15px" v-else >Список постов пуст</h2>
  <post-item
      v-for = "post in posts"
      :post = "post"
      :key = "post.id"
      @remove = "$emit('remove', post)"
  />

</template>

<script>
import PostItem from "@/Components/PostItem";
export default {
  components: {PostItem},
  props:{
    posts:{
      type:Array,
      required:true
    }
  }
}
</script>

<style scoped>
div{
  margin-top:15px ;
}
</style>