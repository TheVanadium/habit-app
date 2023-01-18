<script>
import PetPlace from './components/PetPlace.vue';
import AdoptButton from './components/AdoptButton.vue';
import AppHeader from './components/AppHeader.vue';
import AdoptMenu from './components/AdoptMenu.vue';
import AppNavigation from './components/AppNavigation.vue';
import HabitShop from './components/HabitShop.vue';

export default {
  name: 'App',
  data () {
    return {
      adoptMenuIsVisible: false,
      currentPage: "Pets",
    }
  },
  components: {
    PetPlace,
    AdoptButton,
    AppHeader,
    AdoptMenu,
    AppNavigation,
    HabitShop,
  },
  methods: {
    goToPage(page) {
      this.currentPage = page
    }
  }
}
</script>

<template>
  <div id="app">
    <AppHeader></AppHeader>
    
    <PetPlace class="page" v-bind:id="(this.currentPage==='Pets')?'active-page':''"></PetPlace>
    <HabitShop class="page" v-bind:id="(this.currentPage==='Shop')?'active-page':''"></HabitShop>

    <AdoptButton @openAdoptMenu="(this.adoptMenuIsVisible = !this.adoptMenuIsVisible)"></AdoptButton>
    <AppNavigation @goToPets="goToPage" @goToShop="goToPage"></AppNavigation>

    <AdoptMenu :style="{ visibility: (adoptMenuIsVisible ? 'visible': 'hidden')}"  @closeAdoptMenu="this.adoptMenuIsVisible = !this.adoptMenuIsVisible"></AdoptMenu>
  </div>
</template>

<style>
/* http://meyerweb.com/eric/tools/css/reset/ 
   v2.0 | 20110126
   License: none (public domain)
*/

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}

/* Custom CSS */
#app {
  height: 100vh;
  display: flex;
  flex-direction: column;
}
#header {
  flex: 1;
}
#active-page {
  display: flex;
}
.page {
  flex: 8;
  display: none;
}
#adopt-button {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}
#navigation {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>