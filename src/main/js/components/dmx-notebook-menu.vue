<template>
  <el-dropdown class="dmx-notebook-menu" size="medium" trigger="click" @command="handle">
    <span class="fa fa-bars"></span>
    <el-dropdown-menu slot="dropdown">
      <el-dropdown-item v-if="!username" command="openLoginDialog" divided>Login</el-dropdown-item>
      <el-dropdown-item v-else command="logout" divided>Logout "{{username}}"</el-dropdown-item>
    </el-dropdown-menu>
  </el-dropdown>
</template>

<script>
export default {

  computed: {

    username () {
      return this.$store.state.login.username
    }

  },

  methods: {
    handle (command) {
      this.$store.dispatch(command)
    }
  }
}
</script>

<style>
.dmx-notebook-menu {
  margin: 3vh;
  font-size: 18px !important;
  color: var(--label-color) !important;
}
</style>
