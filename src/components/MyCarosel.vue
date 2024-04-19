<template>
    <div class="section__carosel">
        <div class="features_carosel">
            <!-- Sử dụng slot để chèn các item -->
            <slot></slot>
        </div>
        <div @click="currentSlide(-1, false)" class="arrow__left">
            <img src="../assets/images/ArrowLeft.png" alt="">
        </div>
        <div @click="currentSlide(1, false)" class="arrow__right">
            <img src="../assets/images/ArrowRight.png" alt="">
        </div>

        <div class="rectangles" v-show="props.datas.isDot">
            <div v-for="(dot, index) in numberOfDots" :key="index" @click="currentSlide(index, true)"
                :class="{ 'active': slideIndex === index, 'rectangles__item': slideIndex !== index }">
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, computed, defineProps, onMounted } from 'vue';

// Định nghĩa props
const props = defineProps({
    datas: {
        type: Array,
        required: true
    },
    step: {
        type: Number,
        required: true
    },
    isDot: {
        required: false
    }
});

// Khai báo các biến ref
const slideIndex = ref(0);

// Tính toán số lượng chấm (dots)
const numberOfDots = computed(() => {
    let dots = [];
    for (let i = 0; i + 3 < props.datas.length; i++) {
        dots.push(i);
    }
    return dots;
});

// Hàm xử lý khi mounted
onMounted(() => {

    showSlides(slideIndex.value);

});

// Hàm xử lý khi click vào nút điều hướng
const currentSlide = (step, isClick) => {
    if (isClick) {
        showSlides(step);
    } else {
        if (slideIndex.value + props.step >= props.datas.length && step === 1) {
            slideIndex.value = 0;
            showSlides(slideIndex.value);
        } else if (slideIndex.value + step < 0 && step === -1) {
            slideIndex.value = props.datas.length - props.step;
            showSlides(slideIndex.value);
        } else {
            showSlides(slideIndex.value + step);
        }
    }
};

// Hàm hiển thị slides
const showSlides = (index) => {
    if (props && props.datas) {
        props.datas.forEach((feature) => {
            feature.isVisible = false;
        });
        let length = index + props.step;
        slideIndex.value = index;
        for (let i = slideIndex.value; i < length; i++) {
            if (i < props.datas.length) {
                // eslint-disable-next-line vue/no-mutating-props
                props.datas[i].isVisible = true;
            }
        }
    }
};
</script>

<style scoped>
.section {
    position: relative;
    width: 100%;
    margin: 0 auto;
    padding-top: 64px;
    padding-bottom: 32px;
}

.features_carosel {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
    margin: 50px auto;
    width: 100%;
}

.rectangles {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 35px auto;
    gap: 7px;
}

.arrow__left {
    position: absolute;
    top: 50%;
    left: 0;
    /* Điều chỉnh vị trí bằng cách thay đổi giá trị của left */
    display: flex;
    align-items: center;
    cursor: pointer;
}

.arrow__right {
    position: absolute;
    top: 50%;
    right: 0;
    /* Điều chỉnh vị trí bằng cách thay đổi giá trị của right */
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
}
</style>