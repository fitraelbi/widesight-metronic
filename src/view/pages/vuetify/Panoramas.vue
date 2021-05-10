<template>
  <div></div>
</template>

<script>
import { SET_BREADCRUMB } from "@/core/services/store/breadcrumbs.module";
export default {
  mounted() {
    this.$store.dispatch(SET_BREADCRUMB, [
      { title: "Project", route: "panoramas" },
      { title: "Panoramas" }
    ]);
  }
};
</script>

<style scoped></style>
