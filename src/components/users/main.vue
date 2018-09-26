<template>
  <div>
    Email: {{email}}
    <p>Localidade: {{localidade}}</p>
    <cc-button/>
  </div>
</template>

<script>
import CcButton from "../button/button";
export default {
  components: {
    CcButton
  },
  computed: {
    email() {
      return this.$store.state.user.email;
    },
    localidade() {
      return this.$store.getters.localidade;
    }
  }
};
</script>

<style>
</style>
