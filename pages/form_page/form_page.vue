<template>
  <div
    class="modal fade"
    id="exampleModal"
    tabindex="-1"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-centered">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
          <button
            type="button"
            class="close"
            data-dismiss="modal"
            aria-label="Close"
          >
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">
          <div class="mb-3">
            <label class="form-label fadeIn first">Name</label>
            <input
              v-model="inputName"
              type="text"
              class="form-control fadeIn first"
              placeholder="nathan joe"
            />
          </div>
          <div class="mb-3">
            <label class="form-label fadeIn second">Email</label>
            <input
              v-model="inputEmail"
              type="email"
              class="form-control fadeIn second"
              placeholder="jhon@gmail.com"
              @blur="validateEmail"
            />
            <br />
            <small v-if="emailError" class="text-danger">{{
              emailError
            }}</small>
          </div>
        </div>
        <div class="modal-footer">
          <button
            type="button"
            :disabled="isDisabled"
            :class="
              isDisabled ? 'btn btn-secondary w-50' : 'btn btn-primary w-50'
            "
            data-dismiss="modal"
            @click="sendData"
          >
            Confirm
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import debounce from 'lodash/debounce'

export default {
  name: 'modalForm',
  data() {
    return {
      inputName: '',
      inputEmail: '',
      emailError: '',
      isDisabled: true,
    }
  },
  methods: {
    sendData() {
      console.log(this.inputName, 'ini input nama')
      console.log(this.inputEmail, 'ini input email')
    },
    validateEmail: debounce(function () {
      if (!this.inputEmail) {
        this.isDisabled = true
        this.emailError = 'Email wajib diisi'
        return
      }
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
      if (!emailRegex.test(this.inputEmail)) {
        this.isDisabled = true
        this.emailError = 'Format email tidak valid'
      } else {
        this.isDisabled = false
        this.emailError = ''
      }
    }, 1000),
  },
  watch: {
    inputEmail() {
      this.validateEmail()
    },
  },
}
</script>

<style scoped></style>
