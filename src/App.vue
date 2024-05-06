<template>
  <the-navbar-vue></the-navbar-vue>
  <div class="container with-nav">
    <router-view></router-view>
  </div>
</template>

<script>
import TheNavbarVue from './components/TheNavbar.vue'


export default {
   data () {
    return {
      isAuth: false
    }
   },
   methods: {
    login (){
      isAuth = true
      this.$router.push('/dashboard')
    },
    loginout(){
      isAuth = false
      this.$router.push("/login")
    }
   },
  components: {TheNavbarVue},
  provide() {
    return {
      emails: [
        {id: 1, theme: 'Купил себе PlayStation 5'},
        {id: 2, theme: 'Выучил Vue Router'},
        {id: 3, theme: 'Хочу изучить весь Vue'},
        {id: 4, theme: 'А следующий блок про Vuex!'},
        {id: 5, theme: 'А что там на счет Vue Hooks?'}
      ]
    }
  }
}
</script>

<style>
</style>
