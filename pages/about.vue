<template>
  <div class="content">
    <div class="about">
      <h2>
        What is Async Data? 
      </h2>
      <div class="row">
        <div class="col-sm-6">
          <img src="/images/img.jpeg">
        </div>
        <p class="col-sm-6">
          Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's
          standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make
          a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting,
          remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing
          Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions
          of Lorem Ipsum.
        </p>
      </div>
      <div class="row">
        <p class="col-sm-6">
          Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's
          standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make
          a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting,
          remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing
          Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions
          of Lorem Ipsum.
        </p>
        <div class="col-sm-6">
          <img src="/images/img2.jpeg">
        </div>
      </div>
    </div>
    <div
      class="join">
      <h4>
        Want to know more...
      </h4>
      <p>
        Leave your email to get more information
      </p>
      <form
          @submit.prevent="send"
      >
        <input
            v-model="email"
            type="email"
            id="email"
            name="email"
            placeholder="Your email..."
            class="form-control"
        >
        <input type="submit" id="submit" name="submit" value="Join us" class="btn btn-primary">
      </form>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {

  data () {
    return {
      email: ''
    }
  },

  methods: {
    send () {
      axios.post('http://apinuxtigor:8888/api/sendemail', {
        email: this.email
      }).then((response) => {
        this.email = ''
        console.log(response)
      }).catch((err) => {
        console.log(err)
      })
    }
  }
}
</script>

<style>
  .content {
    width: 80%;
    margin: 2rem auto 0 auto;
  }

  h2 {
    text-align: center;
    margin: 10% 0;
  }

  .row {
    margin-bottom: 10%;
  }

  img {
    padding: 0.5rem 0 0 20%;
  }

  .join {
    margin-bottom: 20%;
  }

  .join h4 {
    margin-left: 10%;
  }

  .join p {
    font-style: italic;
    margin-left: 30%;
  }

  #email {
    margin-left: 55%;
    width: 300px;
  }

  #submit {
    width: 8%;
    margin-top: 10px;
    margin-left: 81%;
  }
</style>
