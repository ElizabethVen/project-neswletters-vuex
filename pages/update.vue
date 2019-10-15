<template>
  <div class="container mt-5">
    <form action>
      <input type="text" v-model="newsletter.title" />
      <textarea v-model="newsletter.description"></textarea>
      <input type="text" v-model="newsletter.target" />
    </form>
    <button @click="updateNewsletter(13)">Actualizar Boletin</button>
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
    updateNewsletter(id) {
      const endpoint =
        'https://newsletters.academlo.com/api/v1/newsletters/' + id
      axios
        .patch(endpoint, this.newsletter)
        .then(() => {
          alert('Todo salió bien')
        })
        .catch(() => {
          alert('Tuvimos un error')
        })
    }
  }
}
</script>
