<template>
  <div class="container mt-5">
    <form action>
      <input type="text" v-model="newsletter.title" />
      <textarea v-model="newsletter.description"></textarea>
      <input type="text" v-model="newsletter.target" />
    </form>
    <button @click="createNewsletter">Crear nuevo boletin</button>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      newsletter: {
        title: '',
        description: '',
        target: ''
      }
    }
  },

  methods: {
    createNewsletter() {
      const endpoint = 'https://newsletters.academlo.com/api/v1/newsletters/'
      axios
        .post(endpoint, this.newsletter)
        .then(() => {
          alert('Creamos exitosamente el nuevo boletin')
        })
        .catch(() => {
          alert('Tuvimos un error')
        })
    }
  }
}
</script>
