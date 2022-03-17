<template>
  <v-card class="list">

    <div class="avatar-container"> 
      <img class="avatar" :src="comm.author.avatar_url">
      <br>
    </div>
    <h1 class="text-center mt-4">{{comm.commit.author.name}}</h1>
    <h4 class="my-4">Email: {{comm.commit.author.email}}</h4>
    <hr>
    <h4 class="mt-4">Commit: </h4>
    <p>{{comm.commit.message}}</p>
    <hr>
    <h4 class="my-4">Date: {{comm.commit.author.date.slice(8,10)+"."+comm.commit.author.date.slice(5,7)+"."+comm.commit.author.date.slice(0,4)+"."}}</h4>
    <v-btn
      @click="emit"
      color="accent"
      elevation="2"
      small>Back</v-btn>
  </v-card>
</template>

<script>
export default {
  name: 'MyCard',
  props: {
    comm: Object,
  },
  data() {
    return {
      checkbox: false,
    }
  },
  methods: {
    emit() {
      this.$emit('btn');
    }
  }
}
</script>

<style lang="scss" scoped>
.list {
  padding: 16px;
  width: 600px;
}
.item {
  margin: 8px;
  padding: 8px;
}
.avatar-container {
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  .avatar {
    width: 200px;
    border-radius: 50%;
  }
}
</style>
