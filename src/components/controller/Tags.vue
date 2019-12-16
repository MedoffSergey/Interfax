<template lang="html">
  <div>
    <div class="tags" @click='showPosts=!showPosts'>
      <span class="tags__title">{{tag.name}}</span>
      <small>
        <div class="tags__description">
          <p >{{tag.description}}</p>
        </div>
      </small>
      <a class="arrow">
        <img v-if='!showPosts' src="https://image.flaticon.com/icons/svg/271/271228.svg" height="20px" width="20px" alt="right arrow">
        <img v-if='showPosts' src="https://image.flaticon.com/icons/png/512/16/16772.png" height="20px" width="20px" alt="bottom arrow">
      </a>
    </div>
    <div>
      <Posts v-if='showPosts' :data="data" />
    </div>
  </div>
</template>


<script>
import Posts from '../../components/controller/Posts.vue'

export default {
  components: {
    Posts
  },
  props: ['tag','showPosts','data'],
  name: 'ControllersShowPost',
  data() {
    return {
    }
  }
}
</script>

<style lang="css" scoped>

.tags {
  border-bottom: 1px solid rgba(0, 0, 0, .3);
  padding: 10px 20px 10px 10px;
  margin: 2px 0;
  display: flex;
}

.tags:hover {
  background-color: #eaeaea;
}

.tags__title {
  text-decoration: inherit;
  color: inherit;
  font-weight: bold;
  padding: 10px 0px;
  font-size: 24px;
  font-family: Titillium Web, sans-serif;
}

.tags__description {
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
