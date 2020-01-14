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
import axios from 'axios'

export default {
  head () {
    return {
      title: 'Some data from API'
    }
  },

  asyncData () {
    return fetch('https://jsonplaceholder.typicode.com/posts')
      .then((response) => {
        const names = response.data
        return { names }
      })
  }
}
</script>
