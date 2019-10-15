<template>
  <div>
    <header>
      <div class="row col-3 header1"><p>[ INSIDE ]</p></div>
      <div class="row p">
        <b-nav v-for="news in tags" :key="news.id">
          <b-nav-item>{{ news.name }}</b-nav-item>
        </b-nav>
        <p>{{ news }}</p>
      </div>
    </header>
    <nuxt />
    <div class="style-foot pie">
      <div class="row">
        <div class="col-6 pad">
          <p>
            Do you like BRAND?
            <span style="color: orange">Advertise with us</span>
          </p>
        </div>
        <div class="col-2"></div>

        <div class="col-2 pad-foot der">
          <p>Developed by:</p>
        </div>

        <div class="col-2 pad-foot color_orange">
          <p class="ong">Elizabeth Ventura Ramírez</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      tags: [],
      link: [
        {
          rel: 'stylesheet',
          href:
            'https://fonts.googleapis.com/css?family=Fjalla+One&display=swap'
        }
      ]
    }
  },
  created() {
    this.extraeApi()
  },
  methods: {
    extraeApi() {
      axios
        .get('https://newsletters.academlo.com/api/v1/tags')
        .then((response) => {
          this.tags = response.data
          console.log(this.tags)
        })
    }
  }
  // components: {
  //   Logo
}
</script>
<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}

.header1 {
  /* display: inline-block; */
  font-family: 'Fjalla One', sans-serif;
  color: rgb(255, 102, 0);
  font-size: 35px;
  margin: 0;
  padding-right: 2px 6px;
}

.style-foot {
  width: 100%;
  background: #f7f7f7;
  display: inline-block;
  font-size: 12px;
}

.color_orange {
  color: #faac58;
}
.der {
  text-align: right;
}

.pad-foot {
  padding-top: 10px;
}
.ong {
  color: orange;
}

.p {
  border-bottom: 1px solid lightgrey;
  /* background-color: lightgrey; */
}
</style>
