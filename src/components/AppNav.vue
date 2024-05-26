<template>
  <nav class="nav-wrapper">
    <ul class="nav-list">
      <app-nav-item :key="item.id" v-for="item in list" :item="item"> </app-nav-item>
    </ul>
  </nav>
</template>

<script lang="ts">
// import AppNavItem from './AppNavItem';
import AppNavItem from '/Users/joes/code/personal/src/components/AppNavItem.vue'
export default {
  name: 'AppNav',
  data() {
    return {
      list: [
        {
          id: 0,
          name: 'Home',
          link: '/'
        }
        // {
        //   id: 1,
        //   name: 'Work',
        //   link: '#work'
        // },
        // {
        //   id: 2,
        //   name: 'About',
        //   link: '#about'
        // },
        // {
        //   id: 3,
        //   name: 'Contact',
        //   link: '#contact'
        // }
      ]
    }
  },
  components: {
    'app-nav-item': AppNavItem
  }
}
</script>

<style lang="scss" scoped>
.nav-wrapper {
  transition: all 0.3s ease-in-out;
  padding-top: 2px;
  opacity: 0.8;
  top: 0;
  position: fixed;
  background-color: white;
  width: 100%;
  height: 56px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.2);
  .nav-list {
    display: flex;
    justify-content: flex-start;
    flex-direction: row;
  }
  &.hidden {
    top: -56px;
    opacity: 0;
  }
}
</style>
