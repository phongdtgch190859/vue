<template>
    <div class="card" v-show="props.card.isVisible">
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
                <img class="card__bottom__color--green" src="../assets/images/LightGreen.png" alt="">
                <img class="card__bottom__color--pink" src="../assets/images/LightPink.png" alt="">
                <img class="card__bottom__color--black" src="../assets/images/Black.png" alt="">
            </div>
            <div class="card__bottom__info">
                <h3>{{ props.card.name }}</h3>
                <p>Price: <span>$ {{ props.card.price }}</span></p>
            </div>
            <div class="d-flex justify-md-space-between ma-3">
                <v-rating v-model="rating" readonly color="yellow darken-3" size="medium" half-increments hover>
                </v-rating>
                <pre>{{ props.card.rating }}</pre>
            </div>
        </div>
    </div>
    <div v-for="(dot, index) in numberOfDots" :key="index" @click="currentSlide(index * 4)"
        :class="{ 'active': slideIndex >= index * 4 && slideIndex < Math.min((index + 1) * 4, features.length), 'rectangles__item': slideIndex < index * 4 || slideIndex >= Math.min((index + 1) * 4, features.length) }">
    </div>
</template>

<script setup>
import { ref } from "vue";

const rating = ref(3.5);
const props = defineProps({
    card: {
        type: Object,
        required: true
    }
});


</script>
<style scoped>
.card {

    transition: opacity 1.5s ease;
    border-radius: 10px;
    background: rgba(255, 255, 255, 1);
    max-width: 270px;

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