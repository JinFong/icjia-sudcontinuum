<template>

<div id="app">

    <div id="outdated"></div>

<navbar />



  <router-view class="view"></router-view>


<my-footer />



</div>
</template>

<script>

import Navbar from '@/components/Navbar'
import MyFooter from '@/components/Footer'


export default {

    name: 'app',
    created: function() {
        //console.log(this.$route.path)
    },
    metaInfo: {
      // if no subcomponents specify a metaInfo.title, this title will be used
      title: 'ICJIA',
      // all titles will be injected into this template
      titleTemplate: 'ICJIA | %s'
    },

    mounted: function() {



        $(function() {


            /////////////////////////////////////////////////////////
            // Outdated browser plugin. Thumbs down on anything less than IE11.
            /////////////////////////////////////////////////////////
            outdatedBrowser({
                bgColor: '#f25648',
                color: '#ffffff',
                lowerThan: 'borderImage',
                languagePath: '/static/outdated-browser/outdatedbrowser/lang/en.html'
            })
        });




    },
    components: {

        MyFooter,
        Navbar
    }
}
</script>

<style lang="scss">

// @import "./scss/base";

.fade-enter-active, .fade-leave-active {
  transition-property: opacity;
  transition-duration: .25s;
}

.fade-enter-active {
  transition-delay: .25s;
}

.fade-enter, .fade-leave-active {
  opacity: 0
}

.btn-modal {z-index: 10000}



</style>
