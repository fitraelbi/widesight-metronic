<template>
  <div
    class="subheader py-2 py-lg-4"
    v-bind:class="subheaderClasses"
    id="kt_subheader"
  >
    <div
      class="d-flex align-items-center justify-content-between flex-wrap flex-sm-nowrap"
      v-bind:class="{ 'container-fluid': widthFluid, container: !widthFluid }"
    >
      <div class="d-flex align-items-center flex-wrap mr-1">
        <h5 class="text-dark font-weight-bold my-2 mr-5">
          {{ title }}
        </h5>
        <ul
          class="breadcrumb breadcrumb-transparent breadcrumb-dot font-weight-bold p-0 my-2"
        >
          <li class="breadcrumb-item">
            <router-link :to="'/'" class="subheader-breadcrumbs-home">
              <i class="flaticon2-shelter text-muted icon-1x"></i>
            </router-link>
          </li>

          <template v-for="(breadcrumb, i) in breadcrumbs">
            <li class="breadcrumb-item" :key="`${i}-${breadcrumb.id}`">
              <router-link
                v-if="breadcrumb.route"
                :key="i"
                :to="breadcrumb.route"
                class="text-muted"
              >
                {{ breadcrumb.title }}
              </router-link>
              <span class="text-muted" :key="i" v-if="!breadcrumb.route">
                {{ breadcrumb.title }}
              </span>
            </li>
          </template>
        </ul>
      </div>
      <div class="d-flex align-items-center">
        <div class="isDashboard" v-if="isDashboard">
          <b-dropdown
            size="sm"
            id="kt_quick_search_toggle"
            variant="link"
            toggle-class="topbar-item text-decoration-none"
            no-caret
            right
            no-flip
          >
            <template v-slot:button-content>
              <div class="btn btn-icon btn-clean btn-lg btn-dropdown mr-1">
                <span class="svg-icon svg-icon-xl svg-icon-primary">
                  <inline-svg src="media/svg/icons/General/Search.svg" />
                </span>
              </div>
            </template>
            <b-dropdown-text tag="div" class="min-w-md-350px">
              <KTSearchDefault></KTSearchDefault>
            </b-dropdown-text>
          </b-dropdown>
          <a
            @click="showModal"
            href="#"
            class="btn btn-light font-weight-bold btn-sm"
          >
            create project
          </a>
        </div>
      </div>
    </div>

    <b-modal ref="modal-create-project" hide-footer title="Create Project">
      <div class="d-block project-form">
        <form>
          <div class="form-group">
            <label for="exampleFormControlInput1">Name Project</label>
            <input class="form-control" id="exampleFormControlInput1" />
          </div>
          <div class="form-group">
            <label for="exampleFormControlTextarea1">Description</label>
            <textarea
              class="form-control"
              v-model="text"
              :maxlength="100"
              id="exampleFormControlTextarea1"
              rows="3"
            ></textarea>
          </div>
        </form>
      </div>
      <div class="row justify-content-md-center">
        <button
          type="button"
          class="btn col-4 btn-modal project-close"
          @click="hideModal"
        >
          Cancel
        </button>
        <button
          type="button"
          class="btn col-4 btn-modal project-create"
          @click="hideModal"
        >
          Create
        </button>
      </div>
    </b-modal>
  </div>
</template>

<style lang="scss">
.custom-v-dropdown {
  &.dropdown-toggle {
    padding: 0;
    &:hover {
      text-decoration: none;
    }

    &.dropdown-toggle-no-caret {
      &:after {
        content: none;
      }
    }
  }

  &.dropdown-menu {
    margin: 0;
    padding: 0;
    outline: none;
    .b-dropdown-text {
      padding: 0;
    }
  }
}

.isDashboard {
  &.dropdown-toggle {
    padding: 0;
    &:hover {
      text-decoration: none;
    }

    &.dropdown-toggle-no-caret {
      &:after {
        content: none;
      }
    }
  }
  .dropdown-menu {
    margin: 0;
    padding: 0;
    outline: none;
    .b-dropdown-text {
      padding: 0;
    }
  }
}
.btn-modal {
  height: 40px;
  margin: 10px;
  font-weight: 500;
}
.project-close {
  color: white;
  background: #f1aeb5;
}
.project-close:hover {
  background: #ea868f;
  color: white;
}
.project-create {
  color: white;
  background: #9ec5fe;
}
.project-create:hover {
  background: #6ea8fe;
  color: white;
}
.project-form {
  margin-left: 30px;
  margin-right: 30px;
  margin-bottom: 50px;
}
</style>

<script>
import KTSearchDefault from "@/view/layout/extras/dropdown/SearchDefault.vue";
import { mapGetters } from "vuex";

export default {
  name: "KTSubheader",
  props: {
    breadcrumbs: Array,
    title: String
  },
  data() {
    return {
      isCountValid: false,
      text: ""
    };
  },
  components: {
    KTSearchDefault
  },
  methods: {
    showModal() {
      if (this.isDashboard) {
        this.$refs["modal-create-project"].show();
      }
    },
    hideModal() {
      if (this.isDashboard) {
        this.$refs["modal-create-project"].hide();
      }
    }
  },
  computed: {
    ...mapGetters(["layoutConfig"]),

    isDashboard() {
      return this.$route.name === "dashboard";
    },
    widthFluid() {
      return this.layoutConfig("subheader.width") === "fluid";
    },

    subheaderClasses() {
      const classes = [];
      const style = this.layoutConfig("subheader.style");
      if (style) {
        classes.push(style);

        if (style === "solid") {
          classes.push("bg-white");
        }

        if (this.layoutConfig("subheader.fixed")) {
          classes.push("border-top");
        }
      }
      return classes.join(" ");
    }
  }
};
</script>
