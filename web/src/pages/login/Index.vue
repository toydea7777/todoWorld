<template lang="pug">
section
  .login-layout
    .form
      
      q-input(v-model="userId" label="아이디" outlined dense )
      q-input(v-model="password" label="비밀번호" @keyup.enter="goto('main')" outlined dense )
      q-btn( @click="goto('main')" color="primary" label="로그인" )
    
</template>

<script>
import { useRouter } from 'vue-router'
import { ref } from 'vue'
export default {
  setup(props) {
    const $router = useRouter()

    const userId = ref('')
    const password = ref('')

    const goto = (path) => {
      console.log(123)
      $router.push(path)
    }

    return {
      goto,
      userId,
      password
    }
  }
}
</script>

<style lang="scss">
.login-layout {
  height: 100vh;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 0 14px;

  .form { 
    width: 100%;
    max-width: 500px;
    border-radius: 8px;
    box-shadow: 1px 1px 7px 3px #ccc;
    padding: 28px 28px;
    
    .q-input { margin-bottom: 14px; }
    .q-btn{ width: 100%; }
  }
}
</style>