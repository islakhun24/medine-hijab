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
          <h5 class="modal-title" id="exampleModalLabel"><i>Contact Us</i></h5>
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
              placeholder="input your name"
            />
          </div>
          <div class="mb-3">
            <label class="form-label fadeIn second">Phone Number</label>
            <div class="input-group fadeIn second">
              <div class="input-group-prepend">
                <span class="input-group-text" id="basic-addon1">+62</span>
              </div>
              <input
                type="text"
                style="border-left: none; padding-left: 0"
                class="form-control"
                v-model="inputPhone"
                placeholder="input your phone number"
                pattern="^[1-9][0-9]*$"
                maxlength="15"
                oninput="if(!this.value.match('^[8][0-9]*$'))this.value=''"
              />
            </div>
            <small class="text-danger fadeIn second"
              >*input starts from number 8</small
            >
          </div>
        </div>
        <div class="modal-footer">
          <button
            type="button"
            :disabled="inputName === '' || inputPhone === ''"
            :class="
              inputName === '' || inputPhone === ''
                ? 'btn btn-secondary w-50'
                : 'btn btn-primary w-50'
            "
            data-dismiss="modal"
            @click="sendData"
          >
            <i class="text-btn">Send</i>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'modalForm',
  data() {
    return {
      inputName: '',
      inputPhone: '',
    }
  },
  methods: {
    sendData() {
      const phoneNumber = '6285163523959'
      const message = `*${this.inputName}* and *${'0' + this.inputPhone}*`
      const url = `https://wa.me/${phoneNumber}?text=${message}`
      window.open(url, '_blank')
    },
  },
}
</script>

<style scoped>
.input-group-text {
  background: transparent;
  border-right: none;
  border-radius: 20px;
}
.modal-title {
  font-family: 'Poppins';
  font-weight: 500;
  font-size: 24px;
}
.text-btn {
  font-family: 'Poppins';
  font-weight: 500;
}
</style>
