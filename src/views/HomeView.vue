<template>
    <TheHeader></TheHeader>
    <TheBanner></TheBanner>

    <TheFeatures></TheFeatures>

</template>
<script>
import { defineComponent } from "vue";
import TheHeader from "../components/TheHeader.vue";
import TheBanner from "../components/TheBanner.vue";
import TheFeatures from "../components/TheFeatures.vue";
export default {
    name: "HomeView",
    components: {
        TheHeader,
        TheBanner,
        TheFeatures,
    }
};

</script>
<style>
.container {}
</style>