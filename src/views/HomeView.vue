<template>
  <div class="home">
    <MyAuth v-model:show="authVisible"/>
  </div>
</template>

<script>
import MyAuth from '@/components/MyAuth.vue'

export default {
  name: 'HomeView',
  components: {
    MyAuth
  },
  data() {
    return {
      authVisible: true
    }
  },
  methods: {
    showAuth() {
      this.authVisible = true
    }
  }
}
</script>
