<template>
    <b-col sm="4">
        <div id="colomn">
            <div id="colomnHeader">
                <span>{{name}}</span>
            </div>
            <TweetCard v-for="(Tweet, i) in Tweets" :key="i" :Tweet='Tweet'/>
        </div>
    </b-col>
</template>

<script>
import TweetCard from './TweetCard.vue'
import axios from 'axios';
export default {
  name: 'Colomn',
  components: {
    TweetCard
  },
  props: {
    name: {
      type: String,
    }
  },
  data() {
    return {
        Tweets: [],
    };
  },
  mounted() {
      axios
        .get('http://localhost:7890/1.1/statuses/user_timeline.json?count=30&screen_name='+this.name)
        .then(response => this.Tweets = response.data)
  }
}
</script>

<style>
#colomn{
    border: 1px solid blue;
    padding: 5px;
    margin-top: 5px;
}
</style>