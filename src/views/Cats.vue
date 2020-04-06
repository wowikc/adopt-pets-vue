<template>
  <div>
    <h1>Cats for Adoption: {{ getAllCats.length}}</h1>
    <b-table striped hover :items="cats">
      <template v-slot:cell(name)="data">
        <router-link :to="`/pet/cats/${data.index}`">
          {{ data.value }}
        </router-link>
      </template>
    </b-table>
  </div>
</template>

<script>
import { mapGetters, mapState } from 'vuex'

export default {
  data() {
    return {}
  },

  computed: {
    ...mapState(['cats']),
    ...mapGetters([
      'animalsCount',
      'getAllCats'
    ])
  }
}
</script>
