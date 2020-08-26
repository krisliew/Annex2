<template>
  <b-navbar class="navBar" toggleable="lg" fixed="top">
    <b-navbar-brand to="/">ANNEX AUTOMATION (M) SDN BHD</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item to="/#About">About</b-nav-item>
        <b-nav-item to="/#Service">Services</b-nav-item>
        <b-nav-item to="/#Contact">Contact</b-nav-item>
      </b-navbar-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-item to="/About">About</b-nav-item>
        <b-nav-item to="/Contact">Contact</b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<script>
export default {}
</script>

<style scoped>
.navBar {
  max-width: 960px;
  margin-left: auto;
  margin-right: auto;
}
</style>
