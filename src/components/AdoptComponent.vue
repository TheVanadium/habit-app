<script>
import AdoptButton from './AdoptButton.vue';
import AdoptMenu from './AdoptMenu.vue';

export default {
    name: 'AdoptComponent',
    data () {
        return {
            adoptMenuIsVisible: false,
        }
    },
    components: {
        AdoptButton,
        AdoptMenu,
    },
}
</script>
<template>
    <div id="adopt-component">
        <AdoptButton @openAdoptMenu="(this.adoptMenuIsVisible = !this.adoptMenuIsVisible)"></AdoptButton>
        <AdoptMenu :style="{ visibility: (adoptMenuIsVisible ? 'visible': 'hidden')}"  @closeAdoptMenu="this.adoptMenuIsVisible = !this.adoptMenuIsVisible"></AdoptMenu>
    </div>
</template>
<style>
    
</style>