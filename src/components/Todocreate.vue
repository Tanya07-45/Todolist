<template>
  <modal>
    <form class="app-form">
      <div class="form-control">
        <label class="label">Title</label>
        <input
          v-model="form.title"
          class="form-input"
          type="text">
      </div>
      <div class="form-control">
        <label class="label">Description</label>
        <textarea
          v-model="form.description"
          cols="30"
          rows="5"
          class="form-input">
        </textarea>
      </div>
      <button
        @click="createTodo"
        type="button"
        class="app-button is-primary">Confirm</button>
    </form>
  </modal>
</template>
<script>
import modal from '@/components/modal'
export default {
     components: {
    modal
  },
  data() {
    return {
       isOpen: false,
      form: {
        title: '',
        description: ''
      }
    }
  },
  methods: {
    createTodo() {
      console.log(this.form)
    }
  }
}

</script>