<template>
  <view class="container">
    <text>Welcome</text>
    <button title="Home" @press="goToHomeScreen"></button>
    <button title="User" @press="goToUserScreen"></button>
  </view>
</template>

<script>
export default {
  // Declare `navigation` as a prop
  props: {
    navigation: {
      type: Object
    }
  },
  methods: {
    goToHomeScreen() {
      this.navigation.navigate("Home")
    },
    goToUserScreen() {
      this.navigation.navigate("User")
    },
  }
}
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
