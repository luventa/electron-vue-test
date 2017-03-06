<template>
  <div>
    <img src="./LandingPageView/assets/logo.png" alt="electron-vue">
    <h1>Welcome.<button @click="test">click me</button></h1>
    <current-page></current-page>
    <versions></versions>
    <links></links>
  </div>
</template>

<script>
import Vue from 'vue'
import Notification from 'vue-bulma-notification'
import CurrentPage from './LandingPageView/CurrentPage'
import Links from './LandingPageView/Links'
import Versions from './LandingPageView/Versions'
console.log(Vue)
console.log(Notification)

const NotificationComponent = Vue.extend(Notification)

const openNotification = (propsData = {
  title: '',
  message: '',
  type: '',
  direction: '',
  duration: 4500,
  container: '.notifications'
}) => {
  return new NotificationComponent({
    el: document.createElement('div'),
    propsData
  })
}

export default {
  components: {
    CurrentPage,
    Links,
    Versions
  },
  methods: {
    test () {
      openNotification({
        title: 'This is a title',
        message: 'This is the message.',
        type: 'success'
      })
    }
  },
  name: 'landing-page'
}
</script>

<style scoped>
  img {
    margin-top: -25px;
    width: 450px;
  }
</style>
