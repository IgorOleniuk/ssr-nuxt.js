<template>
  <div class="container">
    <ul>
      <li
        v-for="name in names"
        :key="name.id"
      >
        {{ name.name }}
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
      .then(json => console.log(json))
  }
}
</script>
