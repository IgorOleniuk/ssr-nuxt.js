<template>
  <header class="header">
      <h1
          class="title"
      >
        <a
            href="/"
        >
          Async Data
        </a>
      </h1>
      <ul>
        <li
            v-if="'/'"
        >
          <nuxt-link
              to="/"
          >
            Home
          </nuxt-link>
        </li>
        <li>
          <nuxt-link
              to="/somedata"
          >
            Some Data
          </nuxt-link>
        </li>
        <li>
          <nuxt-link
              to="/about"
          >
            About
          </nuxt-link>
        </li>
      </ul>
  </header>
</template>

<script>
export default {
  name: 'NavBar'
}
</script>

<style>
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 1rem;
    border-bottom: 2px solid #ccc;
  }

  .header .title {
    font-size: 2rem;
    color: #526488;
  }

  .header .title a {
    color: #526488;
    text-decoration: none;
    font-weight: normal;
  }

  .header ul {
    display: flex;
  }

  .header li a {
    display: inline-block;
    color: #526488;
    padding: 0.3rem 1rem;
    margin-right: 0.5rem;
  }

  li {
    list-style: none;
  }
</style>
