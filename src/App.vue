<script>
import PetPlace from './components/PetPlace.vue';
import AdoptButton from './components/AdoptButton.vue';
import AppHeader from './components/AppHeader.vue';
import AdoptMenu from './components/AdoptMenu.vue';

export default {
  name: 'App',
  data () {
    return {
      adoptMenuIsVisible: false
    }
  },
  components: {
    PetPlace,
    AdoptButton,
    AppHeader,
    AdoptMenu,
  },
  methods: {
    toggleAdoptMenuVisibility() {
      this.adoptMenuIsVisible = !this.adoptMenuIsVisible
      console.log("toggleAdoptMenuVisibility")
    }
  }
}
</script>

<template>
  <div id="app">
    <AppHeader></AppHeader>
    <PetPlace></PetPlace>
    <AdoptButton @openAdoptMenu="toggleAdoptMenuVisibility"></AdoptButton>
    <AdoptMenu :style="{ visibility: (adoptMenuIsVisible ? 'visible': 'hidden')}"  @closeAdoptMenu="toggleAdoptMenuVisibility"></AdoptMenu>
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
/* flexbox make header 10% of height, pet-place 80%, adopt-button 10% */
#app {
  height: 100vh;
  display: flex;
  flex-direction: column;
}
#header {
  flex: 1;
}
#pet-place {
  flex: 8;
  display: flex;
  justify-content: center;
  align-items: center;
}
#adopt-button {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>