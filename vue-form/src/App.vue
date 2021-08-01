<template>
  <div>
    <form v-on:submit.prevent='submitForm'>
      <div>
        <label for="username">ID: </label>
        <input id='username' type="text" v-model='username'>
      </div>
      <div>
        <label for="password">PW: </label>
        <input id='password' type="password" v-model='password'>
      </div>
      <button v-bind:disabled='!isUsernameVaild' type='submit'>로그인</button>
    </form>
    <p v-if='isError'>올바르지 않은 ID입니다</p>
    <p v-if="isUsernameVaild">이메일 형식이 맞습니다</p>
  </div>
</template>

<script>
// 이메일 형식 체크 함수
function validateEmail(email) {
    const re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    return re.test(String(email).toLowerCase());
}

export default {
  data() {
    return {
      username:'',
      password:'',
      isError:false
    }
  },
  computed: {
    isUsernameVaild() {
      return validateEmail(this.username)
    }
  },
  methods: {
    submitForm() {
      console.log('로그인')
      this.isError = true
      // this.initForm()
    },
    initForm(){
      this.username = ''
      this.password = ''
    }
  }  
}
</script>

<style>

</style>