<template>
<NavbarItem></NavbarItem>
<div>
    <h1>Home</h1>
</div>

<FooterItem></FooterItem>
</template>

<script>
import NavbarItem from '../components/NavbarItems.vue';
import FooterItem from '../components/FooterITems.vue';

import {
    defineComponent
} from 'vue';
export default defineComponent({
    name: 'HomeView',
    components: {
        NavbarItem,
        FooterItem
    },
});
</script>
