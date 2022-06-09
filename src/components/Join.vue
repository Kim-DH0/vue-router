<template>
  <h1>{{title}}</h1>
  <form action="./" ref="frm" method="get" class="container">
    <div class="form-group">
      <label class="form-label mt-4">Join</label>
      <div class="form-floating mb-3">
        <input type="text" class="form-control" name="id" ref="id" id="id" placeholder="name@example.com">
        <label for="id" class="title">ID</label>
    </div>
    </div>

    <div class="form-floating mb-3">
      <input type="text" class="form-control" name="name" ref="name" id="name" placeholder="name@example.com">
      <label for="id" class="title">Name</label>
    </div>

     <div class="form-floating mb-3">
      <input type="password" class="form-control" name="pass" ref="pass" id="pass" placeholder="name@example.com">
      <label for="pass" class="title">Password</label>
    </div>

     <div class="form-floating mb-3">
      <input type="password" class="form-control" ref="repass" id="repass" placeholder="name@example.com">
      <label for="repass" class="title">RePassword</label>
    </div>

    <div class="hobbyBox">
      <label class="hobby">Hobby</label>
      <label :for="item" v-for="(item, i) in hobbyList" :key="i">
        {{item}}<input type="checkbox" name="hobby" id="item" value="item">
    </label>
    </div>

    <div class="genderBox">
      <label class="gender">Gender</label>
      <label :for="item" v-for="(item, i) in genderList" :key="i">
        <input type="radio" name="gender" :id="item" :ref="item" :value="item" v-model="gender">{{item}}
    </label>
    </div>

    <div class="plz">
      <label for="id">Mobile</label>
      <div class="plz1">
      <select v-model="mobile" ref="m1" class="plz-1" name="mobile" id="mobile">
        <option :value="item" v-for="(item, i) in mobileList" :key="i">{{item}}</option>
      </select> - <input type="text" ref="m2" id="mobile1" class="m1"> - <input type="text" ref="m3" class="m1" id="mobile2"></div>
      <input type="hidden" ref="mobile">
    </div>

    <div class="btn">
      <label class="title"></label>
      <button ref="btnJoin"  @click.prevent="join" type="button" class="btn btn-primary">Jogin</button>
      <button ref="btnCancel" class="btn btn-primary" v-on:click.prevent="cancel" type="submit">Cancel</button>
    </div>
  </form>
</template>

<script>
import { ref } from '@vue/reactivity';
export default {
  name: 'ToJoin',
  setup() {
    const title = ref('Join')
    return {title}
    },
  data: () => ({
    hobby: [],
    hobbyList: ['축구', '배구', '농구'],
    gender: '여',
    genderList: ['남', '여'],
    mobile: '010',
    mobileList: ['010', '011', '016']
  }),
  methods: {
    join() {
      const frm = this.$refs.frm
      const id = this.$refs.id
      const name = this.$refs.name
      const pass = this.$refs.pass
      const repass = this.$refs.repass
      const m1 = this.$refs.m1
      const m2 = this.$refs.m2
      const m3 = this.$refs.m3
      const mobile = this.$refs.mobile
      
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

      if(name.value=="") {
        alert("이름을 입력하세요")
        name.focus()
        return
      }

      if(pass.value=="") {
        alert("비밀번호를 입력하세요")
        pass.focus()
        return
      }

      if(pass.value!==repass.value) {
        alert("비밀번호가 서로 다릅니다")
        pass.value=""
        repass.value=""
        pass.focus()
        return
      }

      if(m2.value=="") {
        alert("전화번호를 입력하세요")
        m2.focus()
        return
      }

      if(m3.value=="") {
        alert("전화번호를 입력하세요")
        m3.focus()
        return
      }
      
      mobile.value = m1.value + m2.value + m3.value;
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
    display: inline-block;
    width: 120px;
    margin: 5px;
    text-align: left;
    }
  .m1 {
    width: 50px;
  }
  .btn-margin {
    margin: 10px;
  }

  .hobbyBox {
    position: relative;
    margin-top: 5px;
    left: 53px;
  }
  .hobby {
    right: 98px;
    position: relative;
  }
  .genderBox {
    position: relative;
    margin-top: 5px;
  }
  .gender {
    right: 82px;
    position: relative;
  }
  .plz {
    padding-top: 6px;
    right: 24px;
    position: relative;
    display: inline-block;
  }
  .plz1 {
    left: 55px;
    position: relative;
    display: inline-block;
  }
  body {
  display: flex;
  align-items: center;
  flex-direction: column;
  background-color: rgba(231, 243, 243, 0.829);
  padding: 20px;
  }
</style>