<template>
  <div id="app">
    <div class="mobile">
      <div class="mobile-skin">
        <div class="skin-overlay"></div>
        <div class="mobile-viewport">
          <div class="bg-gray-100 canvas">
            <!-- header -->
            <app-header></app-header>
            <!-- header end -->
            <div class="content">
              <!-- content -->

              <router-view></router-view>
              <!-- content end -->
            </div>
            <!-- router links navigation -->
            <app-footer></app-footer>
            <!-- router links navigation end -->
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// GLOBAL IMORTS
import Footer from './components/TheFooter'
import Header from './components/TheHeader'

export default {
  name: 'App',
  components: {
    'app-header': Header,
    'app-footer': Footer
  },
  created() {
    // add data to application
    this.$store.dispatch('initBoroughs')
    this.$store.dispatch('initCategories')
    this.$store.dispatch('initPlaces')
    this.$store.dispatch('initUsers')
    this.$store.dispatch('initReviews')
  }
}
</script>

<style>
  body {
    background-color: rgb(22, 26, 36);
    margin: 0px auto;
  }

  .mobile {
    outline: none;
    position: relative;
    min-width: 100vw;
  }

  .mobile-skin {
    position: relative;
    background-size: 100% !important;
    background-position: 50% !important;
    margin: 0 auto;
    width: 420px;
    height: 855px;
    margin-top: 100px;
    margin-bottom: 100px;
  }

  .skin-overlay {
    background: url('./assets/images/iphone-screen.png');
    background-size: 100%;
    position: absolute;
    width: 100%;
    height: 100%;
    
  }

  .mobile-viewport {
    overflow: hidden;
    display: block;
    position: absolute;
    width: 375px;
    height: 812px;
    z-index: 10;
    left: 22px;
    top: 20px;
  }

  .canvas {
    height: 100%;
    border-bottom-left-radius: 40px;
    border-bottom-right-radius: 40px;
    border-top-left-radius: 40px;
    border-top-right-radius: 40px;
  }

  .content {
    height: 653px;
    overflow-y: auto;
  }

  .nav {
    border-bottom-left-radius: 40px;
    border-bottom-right-radius: 40px;
  }

  .header {
    border-top-left-radius: 38px;
    border-top-right-radius: 38px;
  }
</style>
