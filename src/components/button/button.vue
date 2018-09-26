<template>
  <div>
    <button :disabled="!hasUser" @click="mudarDados">Mudar Dados</button>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  methods: {
    mudarDados() {
      const payload = {
        name: "Outro nome",
        email: "email@email.com",
        level: "usuario-raso",
        city: "Goiania",
        state: "GO"
      };
      // this.$store.commit("CHANGE_USER", payload);
      this.changeUser(payload);
    },
    ...mapActions(["changeUser"])
  },
  computed: {
    hasUser() {
      return this.$store.state.user.name !== "";
    }
  }
};
</script>

<style>
</style>
