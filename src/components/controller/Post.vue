<template lang="html">
  <div class="" @click='showInfo=!showInfo'>
    <div class="posts">

      <div class="summary__method" >
        POST
      </div>
      <small class="summary__description">
        <p>{{posts.description}}</p>
      </small>
      <img class="summary__icon" src="https://image.flaticon.com/icons/png/512/240/240064.png" alt="grey lock" >
    </div>
    <div v-if='showInfo'>
      <ShowInfo/>
    </div>
  </div>
</template>

<script>
import ShowInfo from '../../components/controller/ShowInfo.vue'
export default {
  components: {
    ShowInfo
  },
  props: ['posts','showInfo']
}
</script>

<style lang="css" scoped>
.posts {
  border-color: #49cc90;
  background: rgba(73,204,144,.1);
  border-radius: 4px;
  margin: 0 0 15px;
  border: 1px solid #49cc90;
  padding: 5px;
  align-items: center;
  cursor: pointer;
  display: flex;
  box-shadow: 0 2px 3px rgba(0,0,0,.19);
}

.summary__method{
  background-color: #49cc90;
  font-size: 14px;
  font-weight: 700;
  min-width: 80px;
  padding: 10px;
  text-align: center;
  border-radius: 3px;
  text-shadow: 0 1px 0 rgba(0,0,0,.1);
  font-family: Titillium Web,sans-serif;
  color: #fff;
}
.summary__description {
  padding: 0 10px;
  flex: auto;
}

.summary__icon {
  width: 20px;
  height: 20px;
  padding-right: 10px;
}
</style>
