<template>
  <div>
      <div v-for="(posts,index) in data.definitions" :key="index">
        <Post :showInfo='showInfo' :posts='posts'/>
      </div>
  </div>
</template>

<script>
import Post from '../../components/controller/Post.vue'

export default {
  components: {
    Post
  },
  props: ['data'],
  name: 'Posts',
  data() {
    return {
      showInfo: false
    }
  }
}
</script>

<style scoped>


</style>
