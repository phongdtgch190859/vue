<template>
    <div class="container">
        <div class="section">
            <div class="title">
                <h1>FEATURES</h1>
            </div>
            <div class="features">
                <TheCart v-for="(card, index) in features" :key="index" :card="card">
                </TheCart>
            </div>
            <div @click="plusSlides(-3)" class="arrow__left">
                <img src="../assets/images/ArrowLeft.png" alt="">
            </div>
            <div @click="plusSlides(3)" class="arrow__right">
                <img src="../assets/images/ArrowRight.png" alt="">
            </div>
            <div class="rectangles">
                <div v-for="(dot, index) in numberOfDots" :key="index" @click="currentSlide(index + 4)"
                    :class="slideIndex / 4 == index + 1 ? 'active' : 'rectangles__item'">
                </div>
            </div>

        </div>
    </div>
</template>

<script>
import { defineComponent, ref } from "vue";
import TheCart from "./TheCart.vue";
export default defineComponent({
    name: "TheFeatures",
    components: {
        TheCart,
    },
    data() {
        return {
            slideIndex: 0,
            timeoutId: null,

            features: [
                {
                    isVisible: true,
                    image: "../assets/images/Item1.png",
                    name: "Jordan",
                    price: 500
                },
                {
                    isVisible: false,
                    image: "../assets/images/Item2.png",
                    name: "Nike",
                    price: 400
                },
                {
                    isVisible: false,
                    image: "../assets/images/Item3.png",
                    name: "Adidas",
                    price: 300
                },
                {
                    isVisible: false,
                    image: "../assets/images/Item4.png",
                    name: "Puma",
                    price: 250
                },
                {
                    isVisible: false,
                    image: "../assets/images/Item5.png",
                    name: "Reebok",
                    price: 200
                },
                {
                    isVisible: false,
                    image: "../assets/images/Item6.png",
                    name: "Under Armour",
                    price: 150
                },
                {
                    isVisible: true,
                    image: "../assets/images/Item1.png",
                    name: "Jordan1",
                    price: 500
                },
                {
                    isVisible: false,
                    image: "../assets/images/Item2.png",
                    name: "Nike2",
                    price: 400
                },
            ]
        }
    },
    computed: {
        numberOfDots() {
            let numberOfDots = [];
            const itemsPerGroup = 4; // Số lượng phần tử muốn hiển thị trong mỗi vòng
            for (let i = 0; i < this.features.length; i += itemsPerGroup) {
                numberOfDots.push(i);
            }
            return numberOfDots;
        }
    },

    mounted() {
        this.showSlides(this.slideIndex);
    },
    methods: {
        currentSlide(step) {
            if (this.slideIndex > this.features.length) {
                this.slideIndex = this.features.length - step;
            }
            if (this.slideIndex == this.features.length) {
                this.slideIndex = 0;
            }


            // Hiển thị slides mới
            this.showSlides(this.slideIndex);;
        },
        plusSlides(step) {

            if (this.slideIndex > this.features.length) {
                this.slideIndex = this.features.length - step;
            }
            if (this.slideIndex == this.features.length) {
                this.slideIndex = 0;
            }


            // Hiển thị slides mới
            this.showSlides(this.slideIndex);
        },

        showSlides(i) {
            console.log("i:" + i)

            this.features.forEach((feature) => {
                feature.isVisible = false;
            });
            let lenght = i + 4;
            // Hiển thị 4 slides kế tiếp từ slideIndex
            for (i; i < lenght; i++) {
                this.features[i].isVisible = true;
            }

            // Tăng slideIndex sau mỗi lượt hiển thị
            this.slideIndex = (this.slideIndex + 4);

            // Thiết lập timeout để tự động chuyển slide sau 5 giây

        }



    }
});
</script>

<style>
.container {
    margin: 0;
    width: 100%;
    height: auto;
    background: #b19da8;
    /* Fallback for older browsers */
    background: radial-gradient(at 8.72% 24.82%, #dfeef8 43.23%, rgba(178, 223, 255, 0.257423) 81.25%, rgba(255, 255, 255, 0) 100%),
        /* Radial Gradient */
        linear-gradient(0deg, rgba(236, 194, 224, 0.8), rgba(239, 226, 240, 0.8)),
        /* Linear Gradient */
        radial-gradient(at 94.72% 35.49%, rgba(190, 112, 255, 0.19) 43.75%, rgba(220, 178, 255, 0.083616) 83.85%, rgba(255, 255, 255, 0) 100%),
        /* Radial Gradient */
        radial-gradient(at 24.13% 80.28%, rgba(251, 202, 251, 0.25) 0%, rgba(243, 239, 246, 0.25) 51.56%, rgba(239, 228, 249, 0.25) 100%);
    /* Radial Gradient */

}


.section {
    position: relative;
    width: 65%;
    margin: 0 auto;
}

.features {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 30px;
    margin-top: 30px;

}



.section {
    padding: 32px 117px;
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
    display: flex;
    align-items: center;
    cursor: pointer;
}

.arrow__right {
    position: absolute;
    top: 50%;
    right: 0;
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