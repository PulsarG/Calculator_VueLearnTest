<template>
  <div class="post">
    <div>
      <div><strong>Название</strong>{{ post.title }}</div>
      <div><strong>Описание</strong>{{ post.body }}</div>
    </div>
    <div class="post__btns">
       <my-button>Delete</my-button>
    </div>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";
export default {
    components: {MyButton},
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style>
.post {
  padding: 15px;
  border: 1px solid black;
  margin-top: 10px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>