<template>
  <div class="container">
    <ul>
      <li>
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
    return fetch('https://jsonplaceholder.typicode.com/posts/1')
      .then(response => response.json())
      .then((json) => {
        const post = json
        console.log(json)
        return { post }
      })
  }
}
</script>
