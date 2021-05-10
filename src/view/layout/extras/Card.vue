<template>
  <div>
    <b-card tag="article" style="width: 250px;" class="mb-2 body">
      <b-card-header class="header">
        <div class="d-flex row">
          <div class="mr-auto p-2 icon-folder">
            <i class="menu-icon fas fa-folder"></i>
          </div>
          <div class="ml-auto-p-2 icon-delete">
            <i class="menu-icon fas fas fa-times"></i>
          </div>
        </div>
      </b-card-header>
      <b-card-body class="body-card">
        <b-card-title
          style="font-size: 25px; margin-bottom: 10px;margin-top: 30px;"
          >Jerome</b-card-title
        >
        <b-card-text>
          Some quick example te
        </b-card-text>
      </b-card-body>
      <b-card-footer class="footer">
        <p class="text-footer">
          <span
            ><i
              style="color: #6b6b6bcc"
              class="menu-icon fas fa-info-circle"
            ></i
          ></span>
          <span> Status : add image panorama</span>
        </p>
        <p class="text-footer">
          <span
            ><i
              style="color: #6b6b6bcc"
              class="menu-icon far fa-calendar-plus"
            ></i
          ></span>
          <span> Date : 12-02-2021</span>
        </p>
      </b-card-footer>
    </b-card>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.header {
  margin-bottom: -50px;
  padding-top: 0px;
  margin-top: -10px;
  background: transparent;
  border: none;
}
.footer {
  padding: 0;
  height: 45px;
  border: none;
  font-size: 4px;
  margin-left: -15px;
  margin-right: -15px;
  margin-bottom: 10px;
}
.body {
  height: 230px;
}
.body-card {
  padding: 0;
  height: 100px;
}
.icon-folder {
  background: #d1dff6;
  color: #92b6f0;
  padding: 8px;
  padding-bottom: 3px;
  border-radius: 20px;
  margin-left: -30px;
  margin-top: -1px;
  height: 30px;
}
.icon-delete {
  margin-right: -23ch;
  
}
.text-footer {
  padding: 2px;
  margin: 1px;
  font-size: 11px;
}

@media screen and (max-width: 990px) {
  .icon-delete {
    margin-right: -20px;
  }
  .body-card {
  margin-top: 40px;
  margin-bottom: 10px;
  
}
}
</style>
