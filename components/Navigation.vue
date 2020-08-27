<template>
  <div class="insideNav" :class="{ 'insideNav--hidden': !showNavbar }">
    <b-navbar toggleable="lg" fixed="top">
      <b-navbar-brand to="/">ANNEX AUTOMATION (M) SDN BHD</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item :to="{ path: '/', hash: '#About' }">About</b-nav-item>
          <b-nav-item :to="{ path: '/', hash: '#Service' }"
            >Services</b-nav-item
          >
          <b-nav-item :to="{ path: '/', hash: '#Contact' }">Contact</b-nav-item>
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-nav-item to="/About">About</b-nav-item>
          <b-nav-item to="/Contact">Contact</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showNavbar: true,
    }
  },
  mounted() {
    window.addEventListener('scroll', this.onScroll)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.onScroll)
  },
  methods: {
    onScroll() {
      const currentScrollPosition =
        window.pageYOffset || document.documentElement.scrollTop
      if (currentScrollPosition < 0) {
        return
      }
      // Stop executing this function if the difference between
      // current scroll position and last scroll position is less than some offset
      if (Math.abs(currentScrollPosition - this.lastScrollPosition) < 30) {
        // document.getElementsByClassName('insideNav')[0].backgroundColor =
        //   'rgba(71, 120, 120, 0)'
        return
      }
      this.showNavbar = currentScrollPosition < this.lastScrollPosition
      this.lastScrollPosition = currentScrollPosition
    },
  },
}
</script>

<style scoped>
.insideNav {
  background-color: white;
  box-shadow: 0 2px 15px rgba(71, 120, 120, 0.5);
  height: 60px;
  transform: translate3d(0, 0, 0);
  transition: 0.1s all ease-out;
  width: 100vw;
  position: fixed;
}
.navbar {
  height: 60px;
  max-width: 960px;
  margin-left: auto;
  margin-right: auto;
}
.navbar.navbar--hidden,
.insideNav--hidden {
  box-shadow: none;
  transform: translate3d(0, -100%, 0);
}
</style>
