<template>
  <div class="container mt-5">
    <button @click="deleteNewsletter(12)">Eliminar Boletin</button>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  methods: {
    deleteNewsletter(id) {
      const endpoint =
        'https://newsletters.academlo.com/api/v1/newsletters/' + id
      axios
        .delete(endpoint)
        .then(() => {
          alert('Se elimino exitosamente el boletin')
        })
        .catch(() => {
          alert('Tuvimos un error')
        })
    }
  }
}
</script>
