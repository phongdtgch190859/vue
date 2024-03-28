<template>
    <div class="container">
        <div class="section">
            <div class="title">
                <h1>FEATURES</h1>
            </div>
            <div class="features">
                <div v-for="(card, index,) in features" :key="index" class="card" v-show="card.isVisible">
                    <div class="card__top">
                        <div class="card__image">
                            <img src="../assets/images/Item1.png" alt="">
                        </div>
                        <div class="card__action">
                            <div class="card__action-left">
                                <img src="../assets/images/Heart.png" alt="">
                            </div>
                            <div class="card__action-right">
                                <img src="../assets/images/Bag2.png" alt="">
                            </div>

                        </div>
                    </div>
                    <div class="card__bottom">
                        <div class="card__bottom__color">
                            <img class=".card__bottom__color--green" src="../assets/images/LightGreen.png" alt="">
                            <img class=".card__bottom__color--pink" src="../assets/images/LightPink.png" alt="">
                            <img class=".card__bottom__color--black" src="../assets/images/Black.png" alt="">
                        </div>
                        <div class="card__bottom__info">
                            <h3>{{ card.name }}</h3>
                            <p>Price: <span>$ {{ card.price }}</span></p>
                        </div>
                    </div>
                </div>
            </div>
            <div @click="plusSlides(-1)" class="arrow__left">
                <img src="../assets/images/ArrowLeft.png" alt="">
            </div>
            <div @click="plusSlides(1)" class="arrow__right">
                <img src="../assets/images/ArrowRight.png" alt="">
            </div>
            <div class="rectangles">
                <div v-for="(dot, index) in numberOfDots" :key="index" @click="currentSlide(index * 4)"
                    :class="slideIndex >= index * 4 && slideIndex < Math.min((index + 1) * 4, features.length) ? 'active' : 'rectangles__item'">
                </div>
            </div>

        </div>
    </div>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
    name: "TheFeatures",

    data() {
        return {
            slideIndex: ref(0),
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
                }
            ]
        }
    },
    computed: {
        numberOfDots() {
            let numberOfDots = [];
            const itemsPerGroup = 4; // Số lượng phần tử muốn hiển thị trong mỗi vòng
            for (let i = 0; i < this.features.length; i++) {
                if (i + itemsPerGroup <= this.features.length) {
                    numberOfDots.push(i);
                }
            }
            return numberOfDots;
        }
    },

    mounted() {
        this.showSlides();
    },
    methods: {
        currentSlide(index) {
            if (index === this.numberOfDots - 1) {
                this.slideIndex = this.features.length - 1;
            } else {
                this.slideIndex = index * 4;
            }
            this.showSlides();
        },
        plusSlides(step) {
            // Tăng slideIndex
            this.slideIndex += step;
            // Nếu slideIndex vượt quá số lượng phần tử, quay lại phần tử đầu tiên
            if (this.slideIndex >= this.features.length) {
                this.slideIndex = 0;
            }
            // Nếu slideIndex là giá trị âm, chuyển đến phần tử cuối cùng
            else if (this.slideIndex < 0) {
                this.slideIndex = this.features.length - 1;
            }
            // Hiển thị slides mới
            this.showSlides();
        },

        showSlides() {
            clearTimeout(this.timeoutId);

            // Ẩn tất cả các slides trước khi hiển thị slides mới
            this.features.forEach((feature) => {
                feature.isVisible = false;
            });

            // Hiển thị 4 slides kế tiếp từ slideIndex
            for (let i = 0; i < 4; i++) {
                let indexToShow = (this.slideIndex + i) % this.features.length;
                this.features[indexToShow].isVisible = true;
            }

            // Tăng slideIndex sau mỗi lượt hiển thị
            this.slideIndex = (this.slideIndex + 1) % this.features.length;

            // Thiết lập timeout để tự động chuyển slide sau 5 giây
            this.timeoutId = setTimeout(this.showSlides, 5000);
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

.card {


    transition: opacity 1.5s ease;
    border-radius: 10px;
    background: rgba(255, 255, 255, 1);
    max-width: 270px;
    max-height: 349px;
    box-shadow: 0px 0px 35px 1px rgba(0, 0, 0, 0.18);
    opacity: 1;
}

.card__top {
    position: relative;
    height: 50%;

}

.card .card__action {
    position: absolute;
    top: 220px;
    right: 17px;
    display: flex;
    gap: 10%;
    align-items: center;
    justify-content: center;
    width: 40%;
}

.card .card__action>div {
    width: 45%;
    height: 100%;
    display: flex;
    justify-content: flex-end;

}

.card .card__action img {
    object-fit: cover;
}

.card__bottom {
    margin: 20px 0 10px 0;
}

.card__bottom__color {
    display: flex;
    gap: 7px;
    justify-content: center;
    align-items: center;
}

.card__bottom__info {

    padding: 0 15px 20px 15px;
}

.card__bottom__info h3 {
    font-size: 20px;
    font-weight: 700;
    line-height: 30px;
}

.card__bottom__info p {
    font-size: 18px;
    font-weight: 600;
    line-height: 22.59px;
    opacity: .5;
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