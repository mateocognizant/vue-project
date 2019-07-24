<template>
  <transition-group>
    <div v-for="infos in info.data" :key="infos.id" class="content">
      <div>
      <h4 class="title">{{infos.title}} <b>{{infos.id}}</b></h4>
      <img class="big-img" src="https://s3.amazonaws.com/revue/profile_covers/images/000/000/268/original/vuejs-news-banner.png?1517945419"/>
      <p class="body">{{infos.body}}</p>
      </div>
    </div>
    </transition-group>
</template>

<script>
import axios from 'axios';
export default {
  name: "fetch-data",
  data() {
    return {
      info: null
    };
  },
  mounted() {
    axios
      .get("http://jsonplaceholder.typicode.com/posts")
      .then(response => (this.info = response));
  }
};
</script>

<style lang="scss">

.big-img{
 width:100%;
}

.content{
 padding:15px;
 border: 1px solid #d2d2d2;
 border-radius: 10px;
 margin: 10px 0 10px 0;
 background-color: #f2f2f2;
}

.title{
  font-size:20px;
  font-weight: 300;
}

.body{
font-size:15px;
}
</style>