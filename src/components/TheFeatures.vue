<template>
    <div class="container__features">
        <div class="section">
            <div class="title">
                <h1>FEATURES</h1>
            </div>
            <div class="features">
                <MyCarosel class="sdhfkjsahfakjsh" :datas="features" :step="4">
                    <!-- Sử dụng slot để chèn nội dung vào Carousel -->
                    <template v-for="(card, index) in features" :key="index">
                        <!-- Truyền dữ liệu cho mỗi item thông qua props -->
                        <TheCart :card="card" />
                    </template>
                </MyCarosel>
            </div>
        </div>
    </div>


    <!-- <div class="container__features">
        <div class="section">
            <div class="title">
                <h1>FEATURES</h1>
            </div>
            <div class="features">
                <slot></slot>
                <TheCart v-for="(card, index) in datas" :key="index" :card="card" />
            </div>
            <div @click="currentSlide(-1, false)" class="arrow__left">
                <img src="../assets/images/ArrowLeft.png" alt="">
            </div>
            <div @click="currentSlide(1, false)" class="arrow__right">
                <img src="../assets/images/ArrowRight.png" alt="">
            </div>

            <div class="rectangles">
                <div v-for="(dot, index) in numberOfDots" :key="index" @click="currentSlide(index, true)"
                    :class="{ 'active': slideIndex === index, 'rectangles__item': slideIndex !== index }">
                </div>
            </div>
        </div>
    </div> -->
</template>

<script setup>
import { ref, computed, onMounted } from 'vue';
import TheCart from "./TheCart.vue";
import MyCarosel from "./MyCarosel.vue"

const slideIndex = ref(0);

const features = ref([
    { isVisible: true, image: "../assets/images/Item1.png", name: "Jordan", price: 500, rating: 1 },
    { isVisible: false, image: "../assets/images/Item2.png", name: "Nike", price: 400, rating: 3.5 },
    { isVisible: true, image: "../assets/images/Item1.png", name: "Jordan", price: 500, rating: 4 },
    { isVisible: false, image: "../assets/images/Item2.png", name: "Nike", price: 400, rating: 2.5 },
    { isVisible: true, image: "../assets/images/Item1.png", name: "Jordan", price: 500, rating: 4.5 },
    { isVisible: false, image: "../assets/images/Item2.png", name: "Nike", price: 400, rating: 5 },
    { isVisible: false, image: "../assets/images/Item2.png", name: "Nike", price: 400, rating: 2.5 },
    { isVisible: true, image: "../assets/images/Item1.png", name: "Jordan", price: 500, rating: 4.5 },
    { isVisible: false, image: "../assets/images/Item2.png", name: "Nike", price: 400, rating: 10 },
    // Bổ sung các feature khác ở đây
]);



// const numberOfDots = computed(() => {
//     let dots = [];

//     for (let i = 0; i + 3 < datas.value.length; i++) {
//         dots.push(i);
//     }
//     return dots;
// });

// onMounted(() => {
//     showSlides(slideIndex.value);
// });

// const currentSlide = (step, isClick) => {
//     console.log(step)
//     if (isClick) {

//         showSlides(step)
//     } else {
//         if (slideIndex.value + 4 >= datas.value.length && step == 1) {
//             slideIndex.value = 0;
//             showSlides(slideIndex.value)
//         } else if (slideIndex.value + step < 0 && step == -1) {
//             slideIndex.value = datas.value.length - 4;
//             showSlides(slideIndex.value)
//         }
//         else {
//             showSlides(slideIndex.value + step);
//         }
//     }



// };

// const showSlides = (index) => {
//     datas.value.forEach((feature) => {
//         feature.isVisible = false;
//     });
//     console.log(index)
//     let length = index + 4;
//     slideIndex.value = index
//     for (let i = slideIndex.value; i < length; i++) {
//         if (i < datas.value.length) {
//             datas.value[i].isVisible = true;
//         }
//     }


// };
</script>

<style scoped>
.container__features {}


.section {
    position: relative;
    width: 85%;
    margin: 0 auto;
    padding-top: 64px;
    padding-bottom: 32px;
}

.features {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 30px;
    margin: 50px auto;

}




.section .title {
    display: flex;
    align-items: center;
    justify-content: center;
    margin: auto 25px;
    color: rgba(26, 11, 91, 1);
    font-family: Mulish;
    font-size: 40px;
    font-weight: 900;
    line-height: 50.2px;


}

/* .rectangles {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 35px auto;
    gap: 7px;
}

.arrow__left {
    position: absolute;
    top: 50%;
    left: -20px;
    display: flex;
    align-items: center;
    cursor: pointer;
}

.arrow__right {
    position: absolute;
    top: 50%;
    right: -20px;
    display: flex;
    align-items: center;
    cursor: pointer;
}

.arrow__left:hover,
.arrow__right:hover {
    background-color: rgba(0, 0, 0, 0.8);
}

.rectangles .rectangles__item {
    width: 20px;
    height: 8px;
    background-color: rgba(55, 182, 233, 1);
    border-radius: 25%;
    transition: background-color 0.6s ease;
    cursor: pointer;
}

.active {
    width: 30px;
    height: 8px;
    background-color: rgba(78, 74, 242, 1);
    border-radius: 25%;
} */
</style>