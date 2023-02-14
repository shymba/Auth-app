<template>
  <div class="auth" v-if="show">
    <div class="auth__content" @click.stop>
      <input placeholder="Login" v-model="login" />
      <input placeholder="Password" v-model="password" />
      <button @click="send">Send</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MyAuth',
  props: {
    show: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      login: '',
      password: '',
    }
  },
  methods: {
    send() {
      if(this.login && this.password) {
        console.log(this.login, this.password)
        this.login = ''
        this.password = ''
        this.$emit('update:show', false)
      } else {
        console.log('fill the inputs')
      }
    }
  }
}
</script>

<style scoped lang="scss">
.auth {
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: rgba(0, 0, 0, .5);
  position: fixed;
  display: flex;

  .auth__content {
    margin: auto;
    background-color: #FFFFFF;
    border-radius: 10px;
    min-height: 50px;
    min-width: 300px;
    padding: 20px;

    display: flex;
    flex-direction: column;

    input {
      padding: 10px 5px;
      margin-bottom: 10px;
    }

    button {
      align-self: center;
    }

  }
}

</style>
