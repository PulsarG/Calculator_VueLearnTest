<template>
  <form @submit.prevent>
    <h4>Create Post</h4>
    <input
      v-model="post.title"
      class="input"
      type="text"
      placeholder="Название"
    />
    <input
      v-model="post.body"
      class="input"
      type="text"
      placeholder="Описание"
    />
    <my-button
      class="btn"
      style="align-self: flex-end; margin-top: 15px"
      @click="createPost"
      >Send</my-button
    >
  </form>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";
export default {
  components: { MyButton },
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>


<style scoped>
form {
  display: flex;
  flex-direction: column;
}

.input {
  width: 100%;
  border: solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}
</style>