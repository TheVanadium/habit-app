<script>
import PetPlace from './components/PetPlace.vue';
import AddPetButton from './components/AddPetButton.vue';
import AppHeader from './components/AppHeader.vue';

export default {
  name: 'App',
  components: {
    PetPlace,
    AddPetButton,
    AppHeader,
  }
}
</script>

<template>
  <div id="app">
    <AppHeader></AppHeader>
    <PetPlace></PetPlace>
    <AddPetButton></AddPetButton>
    <router-view></router-view>
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
#header {
  height: 10vh;
}
#pet-place {
  height: 80vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
#add-pet-button {
  height: 10vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>