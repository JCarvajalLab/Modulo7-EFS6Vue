<template>
<NavbarItem></NavbarItem>
<v-main class="home">
    <div class="home-background">
        <v-container class="text-center">
            <div class="texto">
            <h1 class="display-1" white--text>Desafia las expectativas de los MOBA</h1>
            <text-h6> Epicos heroes y accion sin cesar en multiples campos de batalla</text-h6>
            <br>
            </div>
            <br>
        </v-container>
    </div>
</v-main>

<FooterItem></FooterItem>
</template>

<script>
import NavbarItem from '../components/NavbarItems.vue';
import FooterItem from '../components/FooterITems.vue';

export default {
    name: 'HeroesView',
    components: {
        NavbarItem,
        FooterItem
    },
};
</script>

<style>

</style>
