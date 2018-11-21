<template>
    <b-col sm="4">
        <div id="colomn">
            <div id="colomnHeader">
                <span>Colomn</span>
                <font-awesome-icon icon="i-cursor" />
            </div>
            <TweetCard v-for="(Tweet, i) in Tweets" :key="i"/>
        </div>
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

<style>
#colomn{
    border: 1px solid blue;
    padding: 5px;
    margin-top: 5px;
}
</style>