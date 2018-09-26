<template>
  <div>
    <h1> Welcome to Vue2</h1>
    <h4>{{user}}</h4>
    <hr>
    <cc-user></cc-user>
  </div>
  
</template>

<script>
import CcUser from "./components/users/main";
import { mapState } from "vuex";
export default {
  name: "CodecastsApp",
  components: {
    CcUser
  },
  data() {
    return {};
  },
  mounted() {
    const payload = {
      name: "Felipe Magalhães",
      email: "fcpmagalhaes@hotmail.com",
      level: "admin-master"
    };
    setTimeout(() => {
      this.$store.commit("CHANGE_USER", payload);
    }, 3000);
  },
  computed: {
    ...mapState({
      // mapState é um metodo helper que permite acessar o state sem this.$store
      user: state => {
        const { name, email } = state.user;
        return `O usuário logado é ${name} e possui o email ${email}.`;
      }
    })
    // user() {
    //   const { name, email } = this.$store.state.user;
    //   return `O usuário logado é ${name} e possui o email ${email}.`;
    // }
  }
};
</script>

<style>
</style>
