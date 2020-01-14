<template>
  <div class="content">
    <div
      v-for="post in posts"
      :key="post.id"
    >
      <h4>
        {{ post.title }}
      </h4>
      <p>
        {{ post.body }}
      </p>
    </div>
  </div>
</template>

<script>

export default {
  head () {
    return {
      title: 'Some data from API'
    }
  },

  asyncData () {
    return fetch('https://jsonplaceholder.typicode.com/posts')
      .then(response => response.json())
      .then((json) => {
        const posts = json
        console.log(json)
        return { posts }
      })
  }
}
</script>

<style>
  .content {
    width: 80%;
  }
</style>
