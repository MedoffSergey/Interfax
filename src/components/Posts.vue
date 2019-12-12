<template >
  <div class class="header__section">
    <div class="wrapper">
      <div class="posts" v-for="(posts,index) in data.definitions" :key="index">
        <small>
          <div class="markdown">
            <p class="posts__description">{{posts.description}}</p>
          </div>
        </small>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['data'],
  name: 'Posts',
  data() {
    return {
      showPosts: false
    }
  }
}
</script>

<style scoped>
.posts {
  border-radius: 4px;
  margin: 0 0 15px;
  border: 1px solid #49cc90;
  padding: 5px;
  align-items: center;
  cursor: pointer;
  display: flex;
  box-shadow: 0 2px 3px rgba(0,0,0,.19);
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
