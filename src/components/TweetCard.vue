<template>
    <b-card
        tag="article"
        style="max-width: 20rem;"
        class="mb-2">
        <p class="card-text">
          {{getText(Tweet.text)}}
        </p>
        <b-img v-if='Tweet.entities.media' :src='Tweet.entities.media[0].media_url' fluid alt="Responsive image" />
        <b-row>
          <b-col sm="">
            <a v-if='Tweet.entities.urls.length > 0' :href="Tweet.entities.urls[0].url"
           class="card-link">{{Tweet.entities.urls[0].url}}</a>
          </b-col>
          <b-col>
            <p class="date">{{getDate(Tweet.created_at)}}</p>
          </b-col>
        </b-row>
          
          
    </b-card>
</template>

<script>
import moment from 'moment';
export default {
  name: 'TweetCard',
  props:{
    Tweet: {
      type: Object,
    }
  },
  methods: {
    getDate (datetime) {
      return moment(datetime).fromNow();
    },
    getText (content) {
      if (content.indexOf('http') === -1) return content
      let words = content.split(' ');
      return words.slice(0, words.length - 1).join(' ');
    }
  }
}
</script>
<style scoped>
.date{
  text-align: right;
  font-size: smaller;
}
.card-link{
  font-size: small;
}
</style>
