<template>
    <TheHeader></TheHeader>
    <TheBanner></TheBanner>
    <div class="container">
        <TheFeatures></TheFeatures>
        <TheCategory></TheCategory>
    </div>
    <TheTrending></TheTrending>
    <TheNew></TheNew>
    <TheFooter></TheFooter>
</template>
<script>
import { defineComponent } from "vue";
import TheHeader from "../components/TheHeader.vue";
import TheBanner from "../components/TheBanner.vue";
import TheFeatures from "../components/TheFeatures.vue";
import TheCategory from "../components/TheCategory.vue";
import TheTrending from "../components/TheTrending.vue";
import TheNew from "../components/TheNew.vue";
import TheFooter from "../components/TheFooter.vue";
export default {
    name: "HomeView",
    components: {
        TheHeader,
        TheBanner,
        TheFeatures,
        TheCategory,
        TheTrending,
        TheNew,
        TheFooter
    }
};

</script>
<style scoped>
.container {
    margin: 0;

    height: auto;
    background: #b19da8;

    background: radial-gradient(at 8.72% 24.82%, #dfeef8 43.23%, rgba(178, 223, 255, 0.257423) 81.25%, rgba(255, 255, 255, 0) 100%),

        linear-gradient(0deg, rgba(236, 194, 224, 0.8), rgba(239, 226, 240, 0.8)),

        radial-gradient(at 94.72% 35.49%, rgba(190, 112, 255, 0.19) 43.75%, rgba(220, 178, 255, 0.083616) 83.85%, rgba(255, 255, 255, 0) 100%),

        radial-gradient(at 24.13% 80.28%, rgba(251, 202, 251, 0.25) 0%, rgba(243, 239, 246, 0.25) 51.56%, rgba(239, 228, 249, 0.25) 100%);
    position: relative;
}
</style>