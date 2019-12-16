<template>
  <section>
    <div>
      <div @click='showPosts=!showPosts' class='section__models'>
        <div class="seciom__models__inline">
          <p>Models</p>
          <a class="arrow">
            <img v-if='!showPosts' src="https://image.flaticon.com/icons/svg/271/271228.svg" height="20px" width="20px" alt="right arrow">
            <img v-if='showPosts' src="https://image.flaticon.com/icons/png/512/16/16772.png" height="20px" width="20px" alt="bottom arrow">
          </a>
        </div>
      </div>
      <div v-for="(posts,index) in data.definitions" :key="index">
        <ModelsShowPost v-if='showPosts' :posts='posts' :data='data' :showPosts='showPosts' />
      </div>
    </div>
  </section>
</template>

<script>
import ModelsShowPost from '../components/ModelsShowPost.vue'

export default {
  components: {
    ModelsShowPost
  },
  props: ['data'],
  name: 'Models',
  data() {
    return {
      showPosts: false
    }
  }
}
</script>

<style scoped>
.section__models {
  margin: 30px 0;
  border: 1px solid rgba(59, 65, 81, .3);
  border-radius: 4px;
}

.seciom__models__inline {
  padding: 0px 20px 0px 10px;
  display: flex;
}

p {
  padding: 0;
  margin: 15px 0;
  font-size: 16px;
  flex: 1;
  font-family: Titillium Web, sans-serif;
  color: #606060;
  font-weight: bold;
}
</style>
