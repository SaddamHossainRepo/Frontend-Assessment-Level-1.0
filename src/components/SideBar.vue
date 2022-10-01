<template>
  <div class="col-md-2">
    <div id="main">
      <div id="content">
        <span class="slide">
          <a href="#" @click="openSlideMenu()">
            <i class="fas fa-bars"></i>
          </a>
        </span>

        <div id="menu" class="nav">
          <a href="#" class="close" @click="closeSlideMenu()">
            <i class="fas fa-times"></i>
          </a>
          <a href="#">Home</a>
          <a href="#">About</a>
          <a href="#">Services</a>
          <a href="#">Portfolio</a>
          <a href="#">Contact</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SideBar",
  methods: {
    openSlideMenu() {
      document.getElementById("menu").style.width = "250px";
      document.getElementById("content").style.marginLeft = "250px";
    },
    closeSlideMenu() {
      document.getElementById("menu").style.width = "0";
      document.getElementById("content").style.marginLeft = "0";
    },
  },
};
</script>

<style lang="scss" scoped>

</style>
