<template>
  <div class="app">
    <post-form
        @create = "createPost"
    />
    <post-list
        :posts = "posts"
        @remove = "removePost"
    />
  </div>
</template>
<script>
import PostForm from "@/Components/PostForm";
import PostList from "@/Components/PostList";
export default {
  components: {PostList, PostForm},
  data(){
    return{
      posts: [
          {id: 1, title: 'Какашки', body: 'Описание поста'},
          {id: 2, title: 'Какашки 2', body: 'Описание поста 2 '},
          {id: 3, title: 'Какашки 3', body: 'Описание поста 3'},
          {id: 4, title: 'Какашки 4', body: 'Описание поста 4'}
      ],
    }
  },
  methods:{
    createPost(post){
      this.posts.push(post)
    },
    removePost(post){
      this.posts = this.posts.filter(p => p.id !== post.id)
    }
  }
}

</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app{
  padding: 20px;
}

</style>