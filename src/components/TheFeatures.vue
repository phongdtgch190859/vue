<template>
    <div class="container__features">
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
    justify-content: space-between;
    align-items: center;
    gap: 30px;
    margin-top: 50px;

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
}
</style>