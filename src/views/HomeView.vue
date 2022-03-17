<template>
  <v-app>
    <v-main>
      
      <div class="main flex items-center justify-center">

        <v-card class="list" v-if="!hide">
          <v-banner
            single-line>
            <b>SHA commits</b> 
          </v-banner>

          <v-card 
            v-for="(commit, i) in commits"
            :key="`key-${i}`"
            class="item">
            <b class="mr-2">{{i+1}}.</b> <a @click="hide=!hide; comm=commit" >{{commit.sha}}</a> 
          </v-card>
        </v-card>

        <myCard v-else :comm="comm" @btn="btn"></myCard>
        
      </div>

    </v-main>
  </v-app>
</template>

<script>
import myCard from '@/components/myCard.vue';
  export default {
    name: 'Home',

    components: {
      myCard
    },

    data() { 
      return {
        commits: [],
        comm: Object,
        hide: false
      }
    },
    async created() {
      const response = await fetch("https://api.github.com/repos/vuejs/vue/commits");
      this.commits = await response.json();
      this.commits = this.commits.slice(0, 10)
    },
    methods: {
      btn() {
        this.hide = !this.hide;
      }
    }
  }
</script>

<style scoped lang="scss">
.main {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
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
