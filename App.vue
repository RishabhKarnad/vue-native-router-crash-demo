<template>
  <app></app>
</template>

<script>
import {
  createAppContainer,
  createStackNavigator,
  createBottomTabNavigator,
} from 'vue-native-router'

import Welcome from './screens/Welcome'
import Home from './screens/Home'
import Settings from './screens/Settings'
import User from './screens/User'
import UserSettings from './screens/UserSettings'

const AppStackNav = createStackNavigator({
  Home,
  Settings,
}, {
  initialRouteName: 'Home',
})

const UserStackNav = createStackNavigator({
  User,
  UserSettings,
}, {
  initialRouteName: 'User',
})

const TabNav = createBottomTabNavigator({
  App: AppStackNav,
  User: UserStackNav,
}, {
  initialRouteName: 'App',
})

const App = createAppContainer(createStackNavigator({
  Tabs: TabNav,
  Welcome,
}, {
  initialRouteName: 'Welcome',
}))

export default {
  components: {
    App,
  },
}
</script>

<style>
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
  flex: 1;
}
.text-color-primary {
  color: blue;
}
</style>
