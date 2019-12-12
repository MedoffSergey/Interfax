<template >
  <section>
    <div class="controllers">
      <div v-for="(posts,index) in data.tags" :key="index">
        <div class="posts" @click='showPosts=!showPosts'>
          <span class="controllers__title">{{posts.name}}</span>
          <small>
            <div class="markdown">
              <p class="controllers__subtitle">{{posts.description}}</p>
            </div>
          </small>
          <a class="arrow">
            <img v-if='!showPosts' src="https://image.flaticon.com/icons/svg/271/271228.svg" height="20px" width="20px" alt="right arrow">
            <img v-if='showPosts' src="https://image.flaticon.com/icons/png/512/16/16772.png" height="20px" width="20px" alt="bottom arrow">
          </a>
        </div>
        <div class="posts__subPost">
          <Posts v-if='showPosts' :data="data" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Posts from '../components/Posts.vue'

export default {
  components: {
    Posts
  },
  props: ['data'],
  name: 'Controllers',
  data() {
    return {
      showPosts: false
    }
  }
}
</script>

<style scoped>
.controllers {
  margin: 20px 0 0 0;
}

.posts {
  border-bottom: 1px solid rgba(0, 0, 0, .3);
  padding: 10px 20px 10px 10px;
  margin: 2px 0;
  display: flex;
}

.posts:hover {
  background-color: #eaeaea;
}

.controllers__title {
  text-decoration: inherit;
  color: inherit;
  font-weight: bold;
  padding: 10px 0px;
  font-size: 24px;
  font-family: Titillium Web, sans-serif;
}

.markdown {
  width: 100%;
  font-size: 14px;
  display: flex;
  box-sizing: border-box;
  padding: 0 10px;
}

small {
  flex: auto;
}
</style>
