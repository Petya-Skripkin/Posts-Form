<template>
  <form class="form" @submit.prevent>
    <h1>Создать пост</h1>
    <input class="input" type="text" v-model="post.head" />
    <input class="input" type="text" v-model="post.description" />
    <my-button class="btn" @click="addPost">Создать</my-button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        head: "",
        description: "",
      },
    };
  },
  methods: {
    addPost() {
      this.post.id = Date.now();
      this.$emit("addPost", this.post);
      this.post = { head: "", description: "" };
    },
  },
};
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
}

.input {
  font-size: 25px;
  border: 1px solid lightgreen;
  margin-bottom: 10px;
  outline: none;
}

.btn {
  align-self: flex-end;
  background-color: lightgreen;
}
</style>