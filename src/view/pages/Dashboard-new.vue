<template>
  <div style="background: red;">
    <div>
      <cardProject />
    </div>
  </div>
</template>

<script>
/* eslint-disable */
    import { SET_BREADCRUMB } from "@/core/services/store/breadcrumbs.module";
    import cardProject from '../layout/extras/Card'
    export default {
        components:{
            cardProject
        },
       computed:{
       
       },
       mounted() {
            this.$store.dispatch(SET_BREADCRUMB, [{ title: "Dashboard" }]);
        }
    }
</script>
