<template>
  <h1>{{title}}</h1>
  <form action="./" ref="frm" method="get" class="container">
    <!-- <div>
      <label for="id" class="title">ID</label>
      <input type="text" ref="id" id="id">
    </div>
    <div>
      <label for="pass" class="title">Password</label>
      <input type="password" ref="pass" id="pass">
    </div> -->

    <!-- <div class="form-group">
      <label for="id" class="title">ID</label>
      <input type="text" class="form-control" ref="id" id="id" placeholder="ID">
    </div>
     <div class="form-group">
      <label for="pass" class="title">Password</label>
      <input type="password" class="form-control" ref="pass" id="pass" placeholder="Password">
    </div> -->
    <div class="form-group">
      <label class="form-label mt-4">Login</label>
    <div class="form-floating mb-3">
      <input type="text" class="form-control" ref="id" id="id" placeholder="name@example.com">
      <label for="id" class="title">ID</label>
    </div>
    </div>

    <div class="form-floating">
      <input type="password" class="form-control" ref="pass" id="pass" placeholder="Password">
      <label for="pass" class="title">Password</label>
    </div>

    <div class="btn">
      <label class="title"></label>
      <!-- <button ref="btnJoin" class="btn-margin" @click.prevent="login">login</button> -->
      <!-- <button ref="btnCancel" class="btn-margin2" v-on:click.prevent="cancel" type="submit">cancel</button> -->
      <button ref="btnJoin"  @click.prevent="login" type="button" class="btn btn-primary">Login</button>
      <button ref="btnCancel" class="btn btn-primary" v-on:click.prevent="cancel" type="submit">Cancel</button>
    </div>
  </form>
</template>

<script>
import { ref } from '@vue/reactivity';
export default {
  name: 'ToLogin',
  setup() {
    const title = ref('Login')
    return {title}
  },
    methods: {
    login() {
      const frm = this.$refs.frm
      const id = this.$refs.id
      const pass = this.$refs.pass
      
      if(frm.value=="") {
          alert("폼을 입력하세요")
          frm.focus()
          return
      }
      if(id.value=="") {
        alert("아이디를 입력하세요")
        id.focus()
        return
      }

      if(pass.value=="") {
        alert("비밀번호를 입력하세요")
        pass.focus()
        return
      }

      frm.submit();
    },
    cancel() {
      this.$refs.frm.reset()
      document.querySelector('#여').checked = true // 단순히 document의 값을 초기화
    }
  }
}
</script>

<style>
  .container {
    background-color: white;
    border-radius: 8px;
  }
  .title {
   
    width: 120px;
    margin: 5px;
  }
  .btn {
   
  
    right: 30px;
  }
  .btn-primary {
    margin: 10px;
  }
  .form-control {
    text-align: center;
  }
</style>