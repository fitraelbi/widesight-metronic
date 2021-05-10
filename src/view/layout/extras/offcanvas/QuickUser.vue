<template>
  <div class="topbar-item">
     <b-dropdown
          size="sm"
          variant="link"
          toggle-class="custom-v-dropdown"
          no-caret
          right
          no-flip
          text="Actions"
          v-b-tooltip.hover="'User Profile'"
        >
        <template v-slot:button-content>
            <a
                class="btn btn-icon w-auto btn-clean d-flex align-items-center btn-lg px-2" 
                data-toggle="dropdown"
              >
          <span
            class="text-muted font-weight-bold font-size-base d-none d-md-inline mr-1"
          >
            Hi,
          </span>
          <span
            class="text-dark-50 font-weight-bolder font-size-base d-none d-md-inline mr-3"
          >
            Sean
          </span>
          <span class="symbol symbol-35 symbol-light-success">
            <img v-if="false" alt="Pic" :src="picture" />
            <span v-if="true" class="symbol-label font-size-h5 font-weight-bold">
              S
            </span>
          </span>
        </a>
           
          </template>
        <div class="navi navi-hover min-w-md-200px">
            <b-dropdown-text tag="div" class="navi-header font-weight-bold">
             <div class="d-flex align-items-center mt-2">
          <div class="symbol symbol-70 mr-5">
            <img class="symbol-label" :src="picture" alt="" />
            <i class="symbol-badge bg-success"></i>
            
          </div>
          <div class="d-flex flex-column">
            <a
              href="#"
              class="font-weight-bold font-size-h6 text-dark-75 text-hover-primary"
            >
              James Jones
            </a>
            <div class="text-muted mt-1" style="font-size: 12px;">Application Developer</div>
            <div class="navi mt-2">
              <a href="#" class="navi-item">
                <span class="navi-link p-0 pb-2">
                  <span class="navi-icon mr-1">
                    <span class="svg-icon svg-icon-lg svg-icon-primary">
                      <!--begin::Svg Icon-->
                      <inline-svg
                        src="media/svg/icons/Communication/Mail-notification.svg"
                      />
                      <!--end::Svg Icon-->
                    </span>
                  </span>
                  <span class="navi-text text-muted text-hover-primary">
                    jm@softplus.com
                  </span>
                </span>
              </a>
            </div>
            
          </div>
        </div>
            </b-dropdown-text>
            <b-dropdown-text
              tag="div"
              class="navi-separator mb-3"
            ></b-dropdown-text>
            <b-dropdown-text tag="div" class="navi-item">
              <a href="#" class="navi-link">
                <span class="navi-icon">
                  <i class="flaticon2-drop"></i>
                </span>
                <span class="navi-text">Recent Orders</span>
              </a>
            </b-dropdown-text>
            <b-dropdown-text tag="div" class="navi-item">
              <a href="#" class="navi-link">
                <span class="navi-icon">
                  <i class="flaticon2-calendar-8"></i>
                </span>
                <span class="navi-text">Support Cases</span>
              </a>
            </b-dropdown-text>
            <b-dropdown-text tag="div" class="navi-item">
              <a href="#" class="navi-link">
                <span class="navi-icon">
                  <i class="flaticon2-telegram-logo"></i>
                </span>
                <span class="navi-text">Projects</span>
              </a>
            </b-dropdown-text>
            <b-dropdown-text tag="div" class="navi-item">
              <a href="#" class="navi-link">
                <span class="navi-icon">
                  <i class="flaticon2-new-email"></i>
                </span>
                <span class="navi-text">Messages</span>
                <span class="navi-label">
                  <span class="label label-success label-rounded">5</span>
                </span>
              </a>
            </b-dropdown-text>
            <b-dropdown-text
              tag="div"
              class="navi-separator mt-3"
            ></b-dropdown-text>
            <b-dropdown-text tag="div" class="navi-footer">
             <button class="btn btn-light-primary btn-bold btn-sm" @click="onLogout"
              style="width:100px;"
             >
              Sign out
            </button>
              <a
                class="btn text-muted  font-weight-bolder btn-sm "
                href="#"
                >Upgrade plan</a
              >
             
            </b-dropdown-text>
          </div>
     </b-dropdown>

  </div>
</template>

<style lang="scss" scoped>
#kt_quick_user {
  overflow: hidden;
}
</style>

<script>
import { LOGOUT } from "@/core/services/store/auth.module";
import KTLayoutQuickUser from "@/assets/js/layout/extended/quick-user.js";
import KTOffcanvas from "@/assets/js/components/offcanvas.js";

export default {
  name: "KTQuickUser",
  data() {
    return {
      list: [
        {
          title: "Another purpose persuade",
          desc: "Due in 2 Days",
          alt: "+28%",
          svg: "media/svg/icons/Home/Library.svg",
          type: "warning"
        },
        {
          title: "Would be to people",
          desc: "Due in 2 Days",
          alt: "+50%",
          svg: "media/svg/icons/Communication/Write.svg",
          type: "success"
        },
        {
          title: "Purpose would be to persuade",
          desc: "Due in 2 Days",
          alt: "-27%",
          svg: "media/svg/icons/Communication/Group-chat.svg",
          type: "danger"
        },
        {
          title: "The best product",
          desc: "Due in 2 Days",
          alt: "+8%",
          svg: "media/svg/icons/General/Attachment2.svg",
          type: "info"
        }
      ]
    };
  },
  mounted() {
    // Init Quick User Panel
    KTLayoutQuickUser.init(this.$refs["kt_quick_user"]);
  },
  methods: {
    onLogout() {
      this.$store
        .dispatch(LOGOUT)
        .then(() => this.$router.push({ name: "login" }));
    },
    closeOffcanvas() {
      new KTOffcanvas(KTLayoutQuickUser.getElement()).hide();
    }
  },
  computed: {
    picture() {
      return process.env.BASE_URL + "media/users/default.jpg";
    }
  }
};
</script>
