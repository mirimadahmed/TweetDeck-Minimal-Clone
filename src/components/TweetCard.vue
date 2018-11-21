<template>
    <b-card :title="Tweet.text"
        img-bottom
        tag="article"
        style="max-width: 20rem;"
        class="mb-2">
        <b-link href="#" class="card-link">{{Tweet.created_at}}</b-link>
    </b-card>
</template>

<script>
export default {
  name: 'TweetCard',
  props:{
    Tweet: {
      type: Object,
    }
  }
}
</script>
<style scoped>
</style>
