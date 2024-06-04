<template>
  <div class="app">
    <h1>Страница с постами</h1>
    <my-button @click="showDialog">Создать пользователя</my-button>
    <my-dialog v-model:show = "dialogVisible">
      <post-form
          @create = "createPost"
      />
    </my-dialog>

    <post-list
        :posts = "posts"
        @remove = "removePost"
    />
  </div>
</template>
<script>
import PostForm from "@/Components/PostForm";
import PostList from "@/Components/PostList";
import MyDialog from "@/Components/UI/MyDialog";
export default {
  components: {MyDialog, PostList, PostForm},
  data(){
    return{
      posts: [
          {id: 1, title: 'Пост 1', body: 'Описание поста'},
          {id: 2, title: 'Пост 2', body: 'Описание поста 2 '},
          {id: 3, title: 'Пост 3', body: 'Описание поста 3'},
          {id: 4, title: 'Пост 4', body: 'Описание поста 4'}
      ],
      dialogVisible: false,
    }
  },
  methods:{
    createPost(post){
      this.posts.push(post)
      this.dialogVisible = false;
    },
    removePost(post){
      this.posts = this.posts.filter(p => p.id !== post.id)
    },
    showDialog(){
      this.dialogVisible = true;
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
h1{
  margin-bottom: 15px;
}

</style>