<template>
  <div class="content">
    <ul>
      <li
        v-for="post in posts"
        :key="post.id"
      >
        {{ post.title }}
      </li>
    </ul>
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
