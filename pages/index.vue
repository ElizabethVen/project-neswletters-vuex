<template>
  <div class="container">
    <div>
      <!--<logo />-->
      <h1 class="title">
        <strong>Real news, curated bye real humans</strong>
      </h1>
      <h5 class="subtitle">
        <strong>
          Packed with the trends, news & links you need to be smart, informed,
          and ahead of the curve.
        </strong>
      </h5>
      <div v-for="news in newsletters" :key="news.id">
        <b-card
          :title="news.title"
          img-src="https://picsum.photos/600/300/?image=25"
          img-alt="Image"
          img-top
          tag="article"
          style="max-width: 20rem;"
          class="mb-2"
        >
          <b-card-text>
            Some quick example text to build on the card title and make up the
            bulk of the card's content.
          </b-card-text>

          <b-button href="#" variant="primary">Go somewhere</b-button>
        </b-card>
      </div>
      <h1 class="title">
        <strong>Up-and-coming</strong>
      </h1>
      <h5 class="subtitle">
        <strong>
          If these newsletters reach their goals (or get a
          <a href="#">sponsorship</a>), we'll bring on expert writters and
          launch them. Vote for all favorites:
        </strong>
      </h5>
      <div>
        <b-card
          title="Card Title"
          img-src="https://picsum.photos/600/300/?image=25"
          img-alt="Image"
          img-top
          tag="article"
          style="max-width: 20rem;"
          class="mb-2"
        >
          <b-card-text>
            Some quick example text to build on the card title and make up the
            bulk of the card's content.
          </b-card-text>

          <b-button href="#" variant="primary">Go somewhere</b-button>
        </b-card>
      </div>
    </div>
  </div>
</template>

<script>
// import Logo from '~/components/Logo.vue'//
import axios from 'axios'

export default {
  data() {
    return {
      newsletters: []
    }
  },
  created() {
    this.extraeApi()
  },
  methods: {
    extraeApi() {
      axios
        .get('https://newsletters.academlo.com/api/v1/newsletters')
        .then((response) => {
          this.newsletters = response.data
          console.log(this.newsletters)
        })
    }
  }
  // components: {
  //   Logo
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 35px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 20px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
