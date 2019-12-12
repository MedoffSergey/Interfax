<template>
  <transition name="modal-fade">
    <div class="modal-backdrop" role="dialog">
      <div class="modal" ref="modal">
        <header class="modal-header">
          <slot name="header">
            <div class="header__title"> Available authorizations </div>

            <button type="button" class="btn-close btn-right" @click="close" aria-label="Close modal">
              x
            </button>
          </slot>
        </header>

        <section class="modal-body">
          <slot name="body">
              <div class=bearer>
                Bearer  (apiKey)
              </div>
              <p>JWT Authorization header using the Bearer scheme. Example: “Authorization: Bearer {token}”</p>
              <p>Name: Authorization</p>
              <p>In: header</p>
              <p>Value:</p>
              <input type="text" name="" value="">
          </slot>
        </section>

        <footer class="modal-footer">
          <slot name="footer">
            <button type="button" class="btn btn__green" >
              <span class="auto__span">
                Authorize
              </span>
            </button>

            <button type="button" class="btn" @click="close" aria-label="Close modal">
              Close me!
            </button>

          </slot>
        </footer>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: 'modal',
  data() {
    return {}
  },
  methods: {
    close(event) {
      this.$emit('close');
    },
  },
}
</script>

<style scoped>
.modal-backdrop {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal {
  background: #ffffff;
  box-shadow: 1px 1px 20px 1px;
  overflow-x: auto;
  display: flex;
  flex-direction: column;
  width: 648px;
}

.modal-header,
.modal-footer {
  padding: 15px;
  display: flex;
}

.modal-header {
  border-bottom: 1px solid #eeeeee;
  justify-content: space-between;
}

.modal-footer {
  border-top: 1px solid #eeeeee;
  margin: 0 auto;
}

.modal-body {
  position: relative;
  padding: 20px 30px;
}

.btn {
  padding: 4px 8px;
  margin: 0 10px 15px 0;
  border-radius: 4px;
  font-size: 14px;
  cursor: pointer;
  color: #3b4151;
  background: transparent;
  border: 2px solid gray;
  line-height: 1;
  font-family: Titillium Web,sans-serif;
  font-weight: 700;
  outline: none;
}

.btn__green {
  border-color: #49cc90;
  color: #49cc90;;
  border-radius: 4px;
}

.btn-close {
  outline: none;
  border: none;
  width: 20px;
  font-size: 20px;
  padding: 0px;
  cursor: pointer;
  font-weight: bold;
  background: transparent;
}



.modal-fade-enter,
.modal-fade-leave-active {
  opacity: 0;
}

.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity 0.3s ease;
}
input {
  margin: 5px 0;
  padding: 8px 10px;
  border-radius: 4px;
  border: 1px solid #d9d9d9;
}

.bearer {
  font-size: 18px;
  font-weight: 600;
  color: #3b4151;
  font-family: Titillium Web,sans-serif;
  margin-bottom: 10px;
}

.header__title {
  font-size: 20px;
  font-weight: 600;
  flex: 1;
}

p {
  font-size: 12px;
  margin: 0 0 5px;
  color: #3b4151;
}
</style>
