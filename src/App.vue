<template>
  <div class="main">
    <my-form @addPost="addPost" />
    <my-post :posts="posts" @remove="removePost" />
  </div>
</template>

<script>
import MyPost from "@/components/MyPost.vue";
import MyForm from "@/components/MyForm.vue";

export default {
  components: {
    MyPost,
    MyForm
  },
  data() {
    return {
      posts: [
        { 
          id: 1,
          head: "Заголовок 1",
          description: `Lorem ipsum, dolor sit amet consectetur adipisicing elit. Praesentium
        nostrum eum iure sunt. Consequatur libero totam vitae! Nisi in soluta
        earum esse beatae magnam commodi, voluptatum dolore dolores unde
        quaerat!`,
        },
        {
          id: 2,
          head: "Заголовок 2",
          description: `Lorem ipsum, dolor sit amet consectetur adipisicing elit. Praesentium
        nostrum eum iure sunt. Consequatur libero totam vitae! Nisi in soluta
        earum esse beatae magnam commodi, voluptatum dolore dolores unde
        quaerat!`,
        },
        {
          id: 3,
          head: "Заголовок 3",
          description: `Lorem ipsum, dolor sit amet consectetur adipisicing elit. Praesentium
        nostrum eum iure sunt. Consequatur libero totam vitae! Nisi in soluta
        earum esse beatae magnam commodi, voluptatum dolore dolores unde
        quaerat!`,
        },
      ],
    };
  },
  methods: {
    addPost(post) {
      this.posts.push(post)
    },
    removePost(post) {
      this.posts = this.posts.filter(a => a.id !== post.id)
    }
  },
};
</script>

<style>
* {
  margin: 0;
  box-sizing: border-box;
  border-radius: 5px;
}

.main {
  padding: 5px 10px;
}
</style>