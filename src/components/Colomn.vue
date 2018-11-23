<template>
    <div id="colomn">
        <div >
            <h5 id="colomnHeader">Tweets by: @{{name}}</h5>
        </div>
        <TweetCard v-for="(Tweet, i) in FilteredTweets" :key="i" :Tweet='Tweet'/>
    </div>
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
    },
    length: {
      type: String,
    }
  },
  data() {
    return {
        Tweets: [],
    };
  },
  computed: {
    FilteredTweets () {
        return this.Tweets.slice(0, parseInt(this.length));
    }
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
    margin-top: 10px;
}
#colomnHeader{
    color: #1da1f2;
}
</style>