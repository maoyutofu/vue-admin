<template>
    <div id="app">
    <div v-bind:class="['skin-blue', 'sidebar-mini', {'sidebar-collapse': isSidebarCollapse}, {'sidebar-open': isSidebarOpen}]" v-on:click="globalEvent">
       <div class="wrapper">

  <!-- Main Header -->
  <header class="main-header">

    <!-- Logo -->
    <a href="#" class="logo">
      <!-- mini logo for sidebar mini 50x50 pixels -->
      <span class="logo-mini"><b>Vue</b>A</span>
      <!-- logo for regular state and mobile devices -->
      <span class="logo-lg"><b>VueA</b>dmin</span>
    </a>

    <!-- Header Navbar -->
    <nav class="navbar navbar-static-top" role="navigation">
      <!-- Sidebar toggle button-->
      <a href="#" class="sidebar-toggle" data-toggle="offcanvas" role="button" v-on:click="sidebarCollapse">
        <span class="sr-only">Toggle navigation</span>
      </a>
      <!-- Navbar Right Menu -->
      <div class="navbar-custom-menu">
        <ul class="nav navbar-nav">
          <!-- User Account Menu -->
          <li v-bind:class="['dropdown', 'user', 'user-menu', {open: isOpen}]">
            <!-- Menu Toggle Button -->
            <a href="#" class="dropdown-toggle" data-toggle="dropdown" v-on:click.stop="userMenuOpen" aria-expanded="false">
              <!-- The user image in the navbar-->
              <img src="./assets/images/avatar.jpg" class="user-image" alt="User Image">
              <!-- hidden-xs hides the username on small devices so only the image appears. -->
              <span class="hidden-xs">Lemon Tea</span>
            </a>
            <ul class="dropdown-menu">
              <!-- The user image in the menu -->
              <li class="user-header">
                <img src="./assets/images/avatar.jpg" class="img-circle" alt="User Image">
                <p>
                  Lemon Tea - Web Developer
                  <small>Member since Dec. 2016</small>
                </p>
              </li>
              <!-- Menu Body -->
              <li class="user-body">
                <div class="row">
                  <div class="col-xs-4 text-center">
                    <a href="#">Followers</a>
                  </div>
                  <div class="col-xs-4 text-center">
                    <a href="#">Sales</a>
                  </div>
                  <div class="col-xs-4 text-center">
                    <a href="#">Friends</a>
                  </div>
                </div>
                <!-- /.row -->
              </li>
              <!-- Menu Footer-->
              <li class="user-footer">
                <div class="pull-left">
                  <a href="#" class="btn btn-default btn-flat">Profile</a>
                </div>
                <div class="pull-right">
                  <a href="#" class="btn btn-default btn-flat">Sign out</a>
                </div>
              </li>
            </ul>
          </li>
        </ul>
      </div>
    </nav>
  </header>
  <!-- Left side column. contains the logo and sidebar -->
  <aside class="main-sidebar">

    <!-- sidebar: style can be found in sidebar.less -->
    <section class="sidebar">

      <!-- Sidebar user panel (optional) -->
      <div class="user-panel">
        <div class="pull-left image">
          <img src="./assets/images/avatar.jpg" class="img-circle" alt="User Image">
        </div>
        <div class="pull-left info">
          <p>Lemon Tea</p>
          <!-- Status -->
          <a href="#"><i class="fa fa-circle text-success"></i> Online</a>
        </div>
      </div>
      <!-- Sidebar Menu -->
      <ul class="sidebar-menu">
        <li class="header">HEADER</li>
        <!-- Optionally, you can add icons to the links -->
        <li><a href="#"><i class="fa fa-pie-chart"></i> <span>Link</span></a></li>
        <li><a href="#"><i class="fa fa-edit"></i> <span>Another Link</span></a></li>
        <li class="treeview active">
          <a href="#"><i class="fa fa-table"></i> <span>Multilevel</span>
            <span class="pull-right-container">
              <i class="fa fa-angle-left pull-right"></i>
            </span>
          </a>
          <ul class="treeview-menu menu-open">
            <li><a href="#">Link in level 2</a></li>
            <li><a href="#">Link in level 2</a></li>
          </ul>
        </li>
      </ul>
      <!-- /.sidebar-menu -->
    </section>
    <!-- /.sidebar -->
  </aside>

  <!-- Content Wrapper. Contains page content -->
  <div class="content-wrapper" v-bind:style="contentWrapperStyle">
    <!-- Content Header (Page header) -->
    <section class="content-header">
      <h1>
        Page Header
        <small>Optional description</small>
      </h1>
      <ol class="breadcrumb">
        <li><a href="#"><i class="fa fa-dashboard"></i> Level</a></li>
        <li class="active">Here</li>
      </ol>
    </section>

    <!-- Main content -->
    <section class="content">

      <!-- Your Page Content Here -->

    </section>
    <!-- /.content -->
  </div>
  <!-- /.content-wrapper -->

  <!-- Main Footer -->
  <footer class="main-footer">
    <!-- Default to the left -->
    <strong>Copyright &copy; 2016 <a href="#">VueAdmin</a>.</strong> All rights reserved.
  </footer>

  <!-- Add the sidebar's background. This div must be placed
       immediately after the control sidebar -->
  <div class="control-sidebar-bg"></div>
</div>
        </div>
<!-- ./wrapper -->
    </div>
</template>

<script>
import './assets/libs/bootstrap/css/bootstrap.min.css'
import './assets/libs/font-awesome/css/font-awesome.min.css'
import './assets/libs/ionicons/css/ionicons.min.css'
import './assets/libs/admin-lte/css/AdminLTE.min.css'
import './assets/libs/admin-lte/css/skins/skin-blue.min.css'
export default {
  name: 'app',
  data () {
    return {
      isSidebarCollapse: false,
      isSidebarOpen: false,
      isOpen: false,
      contentWrapperStyle: {
        'min-height': window.innerHeight - 100 - 1 + 'px'
      }
    }
  },
  methods: {
    sidebarCollapse () {
      if (window.innerWidth <= 768) {
        this.isSidebarOpen = !this.isSidebarOpen
      } else {
        this.isSidebarCollapse = !this.isSidebarCollapse
      }
    },
    userMenuOpen () {
      this.isOpen = !this.isOpen
    },
    globalEvent () {
      if (this.isOpen) {
        this.isOpen = false
      }
    }
  }
}
</script>

<style>
.main-sidebar {
    position: 'fixed';
    max-height: '100%';
    overflow: 'auto';
    padding-bottom: '50px';
}
</style>