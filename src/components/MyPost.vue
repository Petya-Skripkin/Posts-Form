<template>
  <div v-if="posts.length > 0">
    <h1>Посты</h1>
    <div class="head" v-for="post in posts" :key="post.id">
      <h2>{{ post.head }}</h2>
      <span>
        {{ post.description }}
      </span>
      <my-button class="btn" @click="$emit('remove', post)">Удалить</my-button>
    </div>
  </div>
  <h1 v-else class="err">Посты не найдены</h1>
</template>

<script>
export default {
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.head {
  display: flex;
  flex-direction: column;
  padding: 5px 10px;
  margin-top: 10px;
  border: 2px solid rgb(0, 184, 0);
}

.btn {
  background-color: lightcoral;
  align-self: flex-end;
}
.err {
  color: darkred;
}
</style>