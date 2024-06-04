<template>
  <div><h3>Список пользователей</h3></div>
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

</style>