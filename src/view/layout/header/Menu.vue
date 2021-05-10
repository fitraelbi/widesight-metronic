<template>
  <ul class="menu-nav">
    <router-link
      to="/dashboard"
      v-slot="{ href, navigate, isActive, isExactActive }"
    >
      <li
        aria-haspopup="true"
        data-menu-toggle="hover"
        class="menu-item"
        :class="[
          isActive && 'menu-item-active',
          isExactActive && 'menu-item-active'
        ]"
      >
        <a :href="href" class="menu-link" @click="navigate">
          <span class="menu-text"> Dashboard </span>
        </a>
      </li>
    </router-link>

    <li
      aria-haspopup="true"
      data-menu-toggle="click"
      class="menu-item menu-item-submenu menu-item-open-dropdown"
      v-bind:class="{ 'menu-item-active': hasActiveChildren('/vue-bootstrap') }"
    >
      <a href="#" class="menu-link menu-toggle">
        <span class="menu-text"> User Management </span>
      </a>
       <div class="menu-submenu menu-submenu-fixed">
        <div class="menu-subnav megamenu" style="width: 200px;">
          <ul class="menu-content">
            <li class="menu-item">
              <h3 class="menu-heading menu-toggle">
                <i class="menu-bullet menu-bullet-dot"><span></span></i>
                <span class="menu-text"> user submenu </span>
                <i class="menu-arrow"></i>
              </h3>
              <ul class="menu-inner">
                <router-link
                  to="/vuetify/alerts"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot"><span></span></i>
                      <span class="menu-text"> Alerts </span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vuetify/avatars"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot"><span></span></i>
                      <span class="menu-text"> Avatars </span>
                    </a>
                  </li>
                </router-link>

              </ul>
            </li>
          </ul>
        </div>
      </div>
    </li>

    <li
      aria-haspopup="true"
      data-menu-toggle="click"
      class="menu-item menu-item-submenu menu-item-open-dropdown"
      v-bind:class="{ 'menu-item-active': hasActiveChildren('vuetify') }"
    >
      <a href="#" class="menu-link menu-toggle">
        <span class="menu-text"> Project </span>
      </a>
      <div class="menu-submenu menu-submenu-fixed">
        <div class="menu-subnav megamenu" style="width: 200px;">
          <ul class="menu-content">
            <li class="menu-item">
              <h3 class="menu-heading menu-toggle">
                <i class="menu-bullet menu-bullet-dot"><span></span></i>
                <span class="menu-text"> project submenu </span>
                <i class="menu-arrow"></i>
              </h3>
              <ul class="menu-inner">
                <router-link
                  to="/vuetify/panoramas"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot"><span></span></i>
                      <span class="menu-text"> Panoramas </span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vuetify/avatars"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot"><span></span></i>
                      <span class="menu-text"> 360 StreetView </span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vuetify/badges"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot"><span></span></i>
                      <span class="menu-text"> Marking Manager </span>
                    </a>
                  </li>
                </router-link>

                <router-link
                  to="/vuetify/buttons"
                  v-slot="{ href, navigate, isActive, isExactActive }"
                >
                  <li
                    aria-haspopup="true"
                    class="menu-item"
                    :class="[
                      isActive && 'menu-item-active',
                      isExactActive && 'menu-item-active'
                    ]"
                  >
                    <a :href="href" class="menu-link" @click="navigate">
                      <i class="menu-bullet menu-bullet-dot"><span></span></i>
                      <span class="menu-text"> Vector Layer </span>
                    </a>
                  </li>
                </router-link>

              </ul>
            </li>
          </ul>
        </div>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  name: "KTMenu",
  methods: {
    hasActiveChildren(match) {
      return this.$route["path"].indexOf(match) !== -1;
    }
  }
};
</script>
