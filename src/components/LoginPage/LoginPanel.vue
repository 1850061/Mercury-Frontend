<template>

  <form @submit.prevent="tryLogin">
    <div class="middle" style="padding-bottom: 1rem !important;">
      <div class="text-center">
        <svg class="inline-block" viewBox="0 0 1024 1024" xmlns="http://www.w3.org/2000/svg" width="60" height="60">
          <path
              d="M1015.376 512c0 277.968-225.376 503.344-503.344 503.344C234.046 1015.344 8.704 789.968 8.704 512c0-277.984 225.344-503.328 503.328-503.328C790 8.672 1015.376 234.016 1015.376 512z"
              fill="#E5E8EC"></path>
          <path d="M280.656 206m-35.328 0a35.328 35.328 0 1 0 70.656 0 35.328 35.328 0 1 0-70.656 0Z"
                fill="#424953"></path>
          <path
              d="M506 256c0 32.032-25.968 58-58 58s-58-25.968-58-58 25.968-57.984 58-57.984 58 25.952 58 57.984zM791.312 213.328c0 32.032-25.938 58-58 58-32 0-58-25.968-58-58s26-57.984 58-57.984c32.064 0 58 25.952 58 57.984zM932.688 554.656c0 32.062-25.968 58-58 58s-58-25.938-58-58c0-32 25.968-57.968 58-57.968s58 25.968 58 57.968zM890 704c0 32.032-25.968 58-58 58s-58-25.968-58-58 25.968-57.968 58-57.968 58 25.936 58 57.968z"
              fill="#424953"></path>
          <path d="M554.688 797.344m-58 0a58 58 0 1 0 116 0 58 58 0 1 0-116 0Z" fill="#424953"></path>
          <path
              d="M442.016 810.656c0 32.062-25.968 58-58 58s-58-25.938-58-58c0-32 25.968-57.968 58-57.968s58 25.968 58 57.968zM271.344 512c0 32.032-25.968 58-58 58s-58-25.968-58-58 25.968-57.984 58-57.984 58 25.952 58 57.984z"
              fill="#424953"></path>
          <path
              d="M512 0C229.25 0 0 229.234 0 512c0 282.782 229.25 512 512 512 282.782 0 512-229.218 512-512C1024 229.234 794.782 0 512 0z m331.876 843.876c-43.126 43.126-93.312 76.968-149.188 100.594-57.844 24.468-119.312 36.876-182.688 36.876s-124.812-12.406-182.656-36.876c-55.906-23.626-106.094-57.468-149.218-100.594-43.094-43.094-76.938-93.312-100.594-149.188C55.062 636.844 42.688 575.406 42.688 512c0-63.376 12.376-124.828 36.844-182.672 23.656-55.876 57.5-106.078 100.594-149.188 43.126-43.126 93.312-76.968 149.218-100.61 57.844-24.454 119.282-36.86 182.656-36.86s124.844 12.406 182.688 36.86c55.876 23.64 106.062 57.484 149.188 100.61 43.126 43.11 76.968 93.312 100.594 149.188 24.468 57.844 36.876 119.296 36.876 182.672 0 63.406-12.406 124.844-36.876 182.688-23.626 55.874-57.47 106.094-100.594 149.188z"
              fill="" p-id="5044"></path>
          <path
              d="M618.688 896c-11.812 0-21.344 9.562-21.344 21.344s9.532 21.312 21.344 21.312c11.75 0 21.312-9.532 21.312-21.312S630.438 896 618.688 896zM298.688 661.344c0 11.782 9.532 21.312 21.312 21.312s21.344-9.532 21.344-21.312S331.782 640 320 640s-21.312 9.562-21.312 21.344zM106.688 512c-11.812 0-21.344 9.562-21.344 21.344s9.532 21.312 21.344 21.312c11.75 0 21.312-9.532 21.312-21.312S118.438 512 106.688 512zM426.688 149.344C438.438 149.344 448 139.782 448 128s-9.562-21.328-21.312-21.328c-11.812 0-21.344 9.546-21.344 21.328s9.532 21.344 21.344 21.344zM725.344 320c-11.782 0-21.344 9.562-21.344 21.344s9.562 21.328 21.344 21.328 21.344-9.546 21.344-21.328S737.126 320 725.344 320zM341.344 213.344c0-35.344-28.656-64-64-64s-64 28.656-64 64 28.656 64 64 64 64-28.656 64-64z m-64 21.328c-11.782 0-21.344-9.562-21.344-21.328S265.562 192 277.344 192c11.75 0 21.344 9.578 21.344 21.344s-9.594 21.328-21.344 21.328zM213.344 448c-35.344 0-64 28.656-64 64s28.656 64 64 64 64-28.656 64-64-28.656-64-64-64z m0 85.344C201.562 533.344 192 523.782 192 512c0-11.75 9.562-21.328 21.344-21.328 11.75 0 21.344 9.578 21.344 21.328 0 11.782-9.594 21.344-21.344 21.344zM618.688 797.344c0-35.344-28.656-64-64-64-35.376 0-64 28.656-64 64s28.626 64 64 64c35.344 0 64-28.656 64-64z m-64 21.312c-11.782 0-21.344-9.562-21.344-21.312S542.906 776 554.688 776c11.75 0 21.312 9.594 21.312 21.344s-9.562 21.312-21.312 21.312zM874.688 490.672c-35.376 0-64 28.656-64 63.984 0 35.376 28.626 64 64 64 35.312 0 64-28.626 64-64 0-35.328-28.688-63.984-64-63.984z m0 85.328c-11.782 0-21.344-9.562-21.344-21.344 0-11.75 9.562-21.312 21.344-21.312 11.75 0 21.312 9.562 21.312 21.312 0 11.782-9.562 21.344-21.312 21.344zM832 640c-35.344 0-64 28.656-64 64s28.656 64 64 64 64-28.656 64-64-28.656-64-64-64z m0 85.344c-11.75 0-21.312-9.562-21.312-21.344 0-11.75 9.562-21.344 21.312-21.344s21.344 9.594 21.344 21.344c0 11.782-9.594 21.344-21.344 21.344zM384 725.344c-47.126 0-85.312 38.188-85.312 85.312S336.876 896 384 896s85.344-38.218 85.344-85.344-38.218-85.312-85.344-85.312z m0 128c-23.532 0-42.656-19.126-42.656-42.688 0-23.5 19.126-42.656 42.656-42.656s42.688 19.156 42.688 42.656c0 23.562-19.156 42.688-42.688 42.688zM448 341.344c47.126 0 85.344-38.204 85.344-85.344 0-47.126-38.218-85.328-85.344-85.328S362.688 208.876 362.688 256c0 47.14 38.188 85.344 85.312 85.344z m0-128c23.532 0 42.688 19.14 42.688 42.656 0 23.532-19.156 42.672-42.688 42.672s-42.656-19.14-42.656-42.672c0-23.516 19.124-42.656 42.656-42.656zM810.688 213.344c0-47.126-38.218-85.344-85.344-85.344S640 166.218 640 213.344s38.218 85.328 85.344 85.328 85.344-38.204 85.344-85.328z m-128 0c0-23.532 19.126-42.672 42.656-42.672S768 189.812 768 213.344 748.876 256 725.344 256s-42.656-19.124-42.656-42.656z"
              fill="" p-id="5045"></path>
        </svg>
      </div>
      <div class="h-2"></div>
      <p class="py-4 pl-4 text-xl font-bold font-sans"> Mercury 校园二手交易平台 </p>
    </div>

    <input type="text" placeholder="学号 / 工号" v-model="sid">
    <input type="password" placeholder="密码" v-model="password">
    <router-link to="/login/register" class="hover:text-green-200"> 新用户？去注册 </router-link>
    <router-link to="#" class="float-right pb-4 hover:text-green-200"> 忘记密码 </router-link>
    <button type="submit"
            class="h-12 bg-gradient-to-r from-blue-400 to-green-300 hover:from-green-200 hover:to-blue-300"
    > 登陆
    </button>

  </form>
</template>

<script>
import {api} from "@/request";
import {useStore} from "vuex"
import {ElMessage} from "element-plus";
import {CookieManager} from "@/cookie";

export default {
  name: "LoginPanel",
  data() {
    return {
      sid: "",
      password: "",
      requestSender: undefined
    }
  },
  props: {
    next: String
  },
  methods: {
    tryLogin() {
      let data = new FormData()
      data.append("userId", this.sid)
      data.append("password", this.password)

      api({
        url: "user/login",
        method: "POST",
        data: data
      }).then(
          // Valid response
          (response) => {
            console.log(response)

            // Success login
            if (response.data['Code'] === '200') {
              let user = response.data.User;  // TODO: if backend changes, modify this
              ElMessage.success({
                message: '欢迎回来，' + user.NickName,
                type: 'success'
              })
              console.log(response.data.Token)
              CookieManager.set("token", response.data.Token, 3600*1000)
              this.store.commit("user/userLogin", user)
              this.$router.push("/")
            }
            // Wrong user id or password
            else {
              ElMessage.error({
                message: '用户名或密码错误',
                type: 'error'
              })
            }
          },

          // No response
          (error) => {
            console.log(error)
            ElMessage.error({
              message: '服务器在开小差...',
              type: 'error'
            })
          })
    }
  },
  setup() {
    console.log("in setup")
    console.log(useStore())
    const store = useStore()
    return {
      store
    }
  },
  mounted() {
    console.log("in login panel, next: ", this.next)
    let token = CookieManager.get("token")
    if (token) {
      let formData = new FormData()
      formData.append('token', token)
      api({
        method: "POST",
        data: formData,
        url: "user/autoLogin"
      }).then((response) => {
        if (response.data["Code"] === "200") {
          let user = response.data.User  // TODO: if changes
          this.store.commit("user/userLogin", user)
          ElMessage.success({
            message: '欢迎回来，' + user.NickName,
            type: 'success'
          })
          if (this.next) {
            this.$router.push(this.next)
          } else {
            this.$router.push("/")
          }
        } else {
          ElMessage.warning({
            message: "登陆过期，请重新登陆",
            type: 'success'
          })
        }
      }, (error) => {
        console.log(error)
        ElMessage.error({
          message: '服务器在开小差...',
          type: 'error'
        })
      })
    }
  }
}
</script>

<style scoped>

form {
  width: 25vw;
  position: relative;
  z-index: 3;
  background-color: rgba(255, 255, 255, .1);
  padding: 35px 30px;
  border-radius: 8px;
  box-shadow: 0 20px 40px rgba(0, 0, 0, .1);
  border: 1px solid rgba(255, 255, 255, .2);
  border-right: 1px solid rgba(255, 255, 255, 0.1);
  border-bottom: 1px solid rgba(255, 255, 255, .1);
  backdrop-filter: blur(20px);
}

input {
  width: 100%;
  height: 50px;
  border-radius: 8px;
  background-color: transparent;
  border: 1px solid rgba(255, 255, 255, .5);
  margin-bottom: 15px;
  padding-left: 15px;
  color: #fff;
  outline: none;
}

input::placeholder {
  color: #fff;
}

input:focus {
  border: 1px solid rgba(255, 255, 255, .2);
}

input:focus::placeholder {
  color: lightgray;
}

label {
  @apply pr-1;
  float: left;
  display: inline-block;
  color: white;
  line-height: 50px;
}

button {
  width: 100%;
  background-size: 200% auto;
  border-radius: 8px;
  color: #fff;
  outline: none;
  cursor: pointer;
  box-shadow: 0 20px 40px rgba(0, 0, 0, .1);
  transition: ease .4s;
}

button:hover {
  background-position: right center;
  color: #fff;
  text-decoration: none;
}

.middle {
  text-align: center;
  align-content: center;
}

.pb-4 {
  padding-bottom: 1rem !important;
}

</style>