<template>
  <nav>
    <div class="nav-items">
      <TheNavbarHeader @toggleMenu="toggleMenu" class="the-header"/>
      <TheSearchBar class="search-bar" />
      <TheCartIcon class="cart-icon" />
      <TheMenuBar :toggle="showMenu" />
    </div>
  </nav>
</template>

<script>
import TheCartIcon from 'components/navbar/TheCartIcon.vue';
import TheSearchBar from 'components/TheSearchBar.vue';
import TheNavbarHeader from 'components/navbar/TheNavbarHeader.vue';
import TheMenuBar from 'components/navbar/TheMenuBar.vue';

export default {
  components: {TheCartIcon, TheSearchBar, TheNavbarHeader, TheMenuBar},
  data() {
    return {
      showMenu: false,
    };
  },
  methods: {
    toggleMenu() {
      this.showMenu = !this.showMenu;
    },
  },
};
</script>


<style scoped>
nav {
  position: fixed-top;
  width: 100%;
  border: none;
  box-shadow: .3rem .3rem .3rem black, -.1rem 0 .1rem black;
  height: 8.2rem;
  background-color: midnightblue;
}

.nav-items {
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  justify-content:space-between;
  align-items:center;
}

button {
  text-decoration: none;
  background-color: green;
  border: black .3rem solid;
  box-shadow: .3rem .3rem .3rem rgba(0, 0, 0, 0.3), -.1rem 0 .1rem rgba(0, 0, 0, 0.3);
  outline: none;
  padding: 0 1rem;
  transition: all ease .2s;
  font-size: 3rem;
}

button:hover {
  background-color: chartreuse;
}

button:active {
  box-shadow: none;
}

.cart-icon {
  margin-right: 2rem;
}

.the-header {
  margin-left: 2rem;
}

/* Search Bar */
@media screen and (max-width: 1024px) {
  .search-bar {
    display: none;
  }
}
</style>
