<template>
    <b-col sm="4">
        <h1>Colomn</h1>
        <TweetCard v-for="(Tweet, i) in Tweets" :key="i"/>
    </b-col>
</template>

<script>
import TweetCard from './TweetCard.vue'

export default {
  name: 'Colomn',
  components: {
    TweetCard
  },
  data() {
    return {
        Tweets: [1,2,3,4,5]
    };
  },
}
</script>
