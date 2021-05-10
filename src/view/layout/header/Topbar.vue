<template>
  <!-- begin:: Header Topbar -->
  <div class="topbar">
    
 

    <!--begin: User Bar -->
    <KTQuickUser></KTQuickUser>
    <!--end: User Bar -->
  </div>
  <!-- end:: Header Topbar -->
</template>

<style lang="scss">

</style>

<script>
import KTQuickUser from "@/view/layout/extras/offcanvas/QuickUser.vue";

export default {
  name: "KTTopbar",
  components: {
    KTQuickUser
  }
};
</script>
