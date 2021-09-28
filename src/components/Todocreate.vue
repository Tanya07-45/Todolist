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
        @click="submitForm"
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
  computed: {
    isFormValid() {
      return this.form.title && this.form.description ? true : false
    }
  },
  methods: {
   submitForm() {
    //    if we write thi.form then it will store empty values
        if (this.isFormValid) {
        this.$emit('formSubmitted', {...this.form})
        this.resetForm()
      }
    },
    resetForm() {
      this.form.title = ''
      this.form.description = ''
     // console.log(this.form)
    }
  }
}

</script>