<template>
    <div class="row">
      <NavBar />
      <SideBar />
      <ChartComponent />
    </div>
</template>

<script>
import NavBar from "./NavBar.vue";
import SideBar from "./SideBar.vue";
import ChartComponent from "./ChartComponent.vue";

export default {
  name: "MasterLayout",
  components: {
    NavBar,
    SideBar,
    ChartComponent,
  },
};
</script>

<style></style>
