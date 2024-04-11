<template>
    <div class="container__news">
        <div class="section__news">
            <div class="section__news__title">
                <h1>NEWS</h1>
            </div>
            <div class="section__news__features">
                <ThePost v-for="(post, index) in features" :key="index" :post="post">
                </ThePost>
            </div>

            <div @click="plusSlides(-2)" class="arrow__left">
                <img src="../assets/images/ArrowLeft.png" alt="">
            </div>
            <div @click="plusSlides(2)" class="arrow__right">
                <img src="../assets/images/ArrowRight.png" alt="">
            </div>

        </div>
    </div>
</template>

<script>
import { defineComponent, ref } from "vue";
import ThePost from "./ThePost.vue";
export default defineComponent({
    name: "TheNew",
    components: {
        ThePost,
    },
    data() {
        return {
            slideIndex: 0,
            timeoutId: null,

            features: [
                {
                    isVisible: true,
                    image: "../assets/images/Item1.png",
                    content: "23% off in all products",

                },
                {
                    isVisible: false,
                    image: "../assets/images/Item2.png",
                    content: "23% off in all productsw",

                },
                {
                    isVisible: false,
                    image: "../assets/images/Item3.png",
                    content: "23% off in all products2",

                },
                {
                    isVisible: false,
                    image: "../assets/images/Item4.png",
                    content: "23% off in all products3",

                },
                {
                    isVisible: false,
                    image: "../assets/images/Item5.png",
                    content: "23% off in all products4",

                },
                {
                    isVisible: false,
                    image: "../assets/images/Item6.png",
                    content: "23% off in all products5",

                },
                {
                    isVisible: true,
                    image: "../assets/images/Item1.png",
                    content: "23% off in all products",

                },
                {
                    isVisible: false,
                    image: "../assets/images/Item2.png",
                    content: "23% off in all products",

                },
            ]
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
            let lenght = i + 3;
            // Hiển thị 4 slides kế tiếp từ slideIndex
            for (i; i < lenght; i++) {
                this.features[i].isVisible = true;
            }

            // Tăng slideIndex sau mỗi lượt hiển thị
            this.slideIndex = (this.slideIndex + 3);

            // Thiết lập timeout để tự động chuyển slide sau 5 giây

        }



    }
});
</script>

<style scoped>
.container__news {
    background-color: white;
}


.section__news {
    position: relative;
    width: 85%;
    margin: 0 auto;
    padding-top: 80px;
    padding-bottom: 32px;

}

.section__news__features {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 40px;
    margin-top: 59px;

}




.section__news__title {
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


.arrow__left {
    position: absolute;
    top: 63%;
    left: -20px;
    display: flex;
    align-items: center;
    cursor: pointer;

}

.arrow__right {
    position: absolute;
    top: 63%;
    right: -20px;
    display: flex;
    align-items: center;
    cursor: pointer;
}

.arrow__left:hover,
.arrow__right:hover {
    background-color: rgba(0, 0, 0, 0.8);
}
</style>