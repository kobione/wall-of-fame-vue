<template>
  <div>
    <h3>Wall Of Fame</h3>
    <p>Wall Of Fame client side implementation using Vue 2.0, Vue-Router 2.0 and Vuex</p>
    <div class="col-sm-4">
      <ul class="list-group">
        <li class="list-group-item" v-for="note in notes">
          {{note.text}}
          <a class="btn btn-default" @click="removeNote" href="#">X</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  // mapActions maps our actions to any property name we want to access
  import { mapActions, mapGetters } from 'vuex';

  export default {
    computed: {
      ...mapGetters({
        notes: 'allNotes'
      })
    },

    methods: {
      ...mapActions({
        removeNote: 'deleteNote'
      })
    }
  }
</script>
