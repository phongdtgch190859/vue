<template>
    <TheHeader></TheHeader>
    <div class="section__product">

        <div class="section__product_left">
            <div class="section__product_left__top">
                <div class="section__product__left__top__image">
                    <img src="../assets/images/ProductItem1.png" alt="">

                </div>
                <div class="section__product_left__top__tags">
                    <button>NEWS</button>
                    <button class="red">TRENDING</button>
                </div>
            </div>
            <div class="section__product_left__bottom">
                <div class="section__product_left__bottom__thumbnails">
                    <div class="section__product_left__bottom__item">
                        <img src="../assets/images/ProductItem1.png" alt="">
                    </div>
                    <div class="section__product_left__bottom__item">
                        <img src="../assets/images/ProductItem1.png" alt="">
                    </div>
                    <div class="section__product_left__bottom__item">
                        <img src="../assets/images/ProductItem1.png" alt="">
                    </div>
                    <div class="section__product_left__bottom__item">
                        <img src="../assets/images/ProductItem1.png" alt="">
                    </div>
                </div>
                <div class="arrow__left">&lt;</div>
                <div class="arrow__right">&gt;</div>
            </div>
        </div>
        <div class="section__product__right">
            <div class="section__product__right__top">
                <div class="section__product__right__top__menu">
                    <p><a href="">Home</a> &gt; <a href="">Lifestyple</a> &gt; <a href="">Snekaer</a> &gt; <a
                            href="">Joedan</a> &gt; <a href="">Nike Blaze</a>
                    </p>
                </div>
                <div class="section__product__right__top__overview">
                    <div class="section__product__right__top__overview__left">
                        <h3>Nike Blaze MID</h3>
                        <span>Nike Store</span>
                    </div>
                    <div class="section__product__right__top__overview__right">
                        <div class="section__product__right__top__overview__right__wishlist">
                            <img src="../assets/images/WishLish.png" alt="">
                            <span>109</span>
                        </div>
                        <img src="../assets/images/Save.png" alt="">
                        <img src="../assets/images/Share.png" alt="">
                    </div>
                </div>
                <div class="section__product__right__top__infos">
                    <div class="section__product__right__top__infos__price">
                        <h3>$179.99</h3>
                        <h2>$279.99</h2>
                    </div>
                    <div class="section__product__right__top__infos__review">
                        <div class="section__product__right__top__infos__review__item">
                            <div class="section__product__right__top__infos__review__rating">
                                <img src="../assets/images/Rating.png" alt="">
                                <span>4.8</span>
                            </div>
                            <div class="section__product__right__top__infos__review__feedback">
                                <img src="../assets/images/Feedback.png" alt="">
                                <span>67 </span>
                                <span>Reviews</span>
                            </div>
                        </div>
                        <p><span>93%</span> of buyers have recommended this</p>
                    </div>
                </div>
            </div>
            <div class="section__product__right__info">
                <div class="section__product__right__info__colors">
                    <h3>Choose a Color</h3>
                    <div class="section__product__right__info__colors--select">
                        <button :style="getButtonStyle('red')" @click="setColor('red')"></button>
                        <button :style="getButtonStyle('blue')" @click="setColor('blue')"></button>
                        <button :style="getButtonStyle('black')" @click="setColor('black')"></button>
                        <button :style="getButtonStyle('white')" @click="setColor('white')"></button>
                        <button :style="getButtonStyle('brown')" @click="setColor('brown')"></button>
                        <div value="selected">
                            <img src="../assets/images/Selected.png" alt="">
                        </div>
                    </div>
                </div>
                <div class="section__product__right__info__sỉzes">
                    <h3>Choose a Size</h3>
                    <div class="section__product__right__info__sizes--select">
                        <ul>
                            <li>36-Female</li>
                            <li>36-Female</li>
                            <li>36-Female</li>
                            <li>36-Female</li>
                            <li>36-Female</li>
                            <li>36-Female</li>
                            <li>36-Female</li>
                            <li>36-Female</li>
                        </ul>
                    </div>
                </div>
                <div class="add">
                    <div class="add_amount">
                        <span>-</span>
                        <span>5</span>
                        <span>+</span>
                    </div>
                    <button>
                        <img src="../assets/images/CartWhile.png" alt="">
                        Add To Cart
                    </button>
                </div>
            </div>
            <div class="section__product__right__bottom">
                <div class="section__product__right__bottom__free">
                    <img src="../assets/images/Delivery.png" alt="">
                    <div>
                        <h3>Free Delivery</h3>
                        <label for="">Enter your Postal code for Delivery Availability</label>
                        <input type="text">
                    </div>
                </div>
                <div class="section__product__right__bottom__return">
                    <img src="../assets/images/CartRed.png" alt="">
                    <div>
                        <h3>Return Delivery</h3>
                        <span>Free 30 days Delivery Return. <a href="#">Details</a></span>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <TheFooter></TheFooter>
</template>
<script>
import { defineComponent } from "vue";
import TheHeader from "../components/TheHeader.vue";

import TheFooter from "../components/TheFooter.vue";
export default {
    selectedColor: null,
    name: "ProductDetail",
    components: {
        TheHeader,
        TheFooter
    },
    methods: {
        setColor(color) {
            this.selectedColor = color;
        },
        getButtonStyle(color) {
            return {
                backgroundColor: color,
            };
        }
    }
};

</script>
<style scoped>
.section__product {
    display: flex;
    width: 88%;
    margin: 0 auto;
    gap: 89px;
    justify-content: space-between;
    background: rgba(255, 255, 255, 1);

}

.section__product_left {
    width: 45%;
    height: 100%;
    display: flex;
    flex-direction: column;
    gap: 75px;
    justify-content: center;
    align-items: center;
    position: relative;
}

.section__product_left__top {

    width: 100%;
    height: 70%;
}

.section__product__left__top__image {
    display: flex;
    justify-content: center;
    border: 1px solid rgba(237, 240, 248, 1);
    border-radius: 17px;

}

.section__product_left__top__tags {
    position: absolute;
    left: 16px;
    top: 17px;
    display: flex;
    gap: 10px
}

.section__product_left__top__tags button {
    box-sizing: content-box;
    font-family: Mulish;
    font-size: 10px;
    font-weight: 700;
    line-height: 12.55px;
    text-align: center;
    width: 70px;
    height: 32px;
    padding: 5px 15px 5px 15px;
    gap: 10px;
    border-radius: 10px;
    border: 1px solid rgba(78, 74, 242, 1);
    opacity: 0px;
    color: white;
    background-color: rgba(107, 157, 251, 1);
}

.section__product_left__top__tags .red {
    background-color: rgba(237, 97, 97, 1);
}

.section__product_left__bottom {
    width: 100%;
    height: calc(30% - 75px);
    position: relative;
    object-fit: cover;
    flex: left;
}

.section__product_left__bottom__thumbnails {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 18px;
}

.section__product_left__bottom .arrow__left {
    font-size: 30px;
    position: absolute;
    left: 0;
    top: 30%;
}

.section__product_left__bottom .arrow__right {
    object-fit: cover;
    box-sizing: border-box;
    font-size: 30px;
    position: absolute;
    right: 0;
    top: 30%;
}

.section__product_left__bottom__item {}



.section__product_left__bottom__item img {
    width: 115px;
    height: 115px;
    border-radius: 14px;
    border: 3px solid linear-gradient(136.22deg, #3A4980 2.59%, rgba(44, 48, 121, 0.2) 97.48%);
}



.section__product__right__top__menu p,
a {
    text-decoration: none;
    opacity: 0px;
    font-family: Mulish;
    font-size: 14px;
    font-weight: 400;
    line-height: 17.57px;
    text-align: left;
    color: rgba(163, 169, 194, 1);
    padding: 0px 8px;
}

.section__product__right__top__menu {

    width: auto;
    height: 30px;
    display: flex;
    align-items: center;
    gap: 14px;
    border-radius: 8px 0px 0px 0px;
    background: rgba(237, 240, 248, 1);


}

.section__product__right__top__overview {
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
    margin-bottom: 15px;

}

.section__product__right__top__overview__left h3 {
    font-family: Mulish;
    font-size: 32px;
    font-weight: 700;
    line-height: 40.16px;
    text-align: left;



}

.section__product__right__top__overview__left span {
    font-family: Mulish;
    font-size: 16px;
    font-weight: 400;
    line-height: 20.08px;
    text-align: left;
}

.section__product__right__top__overview__right {
    display: flex;
    height: 34px;
    gap: 13px;
    justify-content: right;
}

.section__product__right__top__overview__right__wishlist {
    display: flex;
    font-family: Inter;
    font-size: 16px;
    font-weight: 600;
    line-height: 19.36px;
    text-align: left;
    color: rgba(212, 111, 119, 1);
    align-items: center;
    justify-content: center;
    gap: 10px;

}

.section__product__right__top__infos {
    display: flex;
    gap: 41px;
}

.section__product__right__top__infos__price {}

.section__product__right__top__infos__price h3 {
    font-family: Mulish;
    font-size: 34px;
    font-weight: 800;
    line-height: 42.67px;
    text-align: left;
    color: rgba(102, 99, 223, 1);

}

.section__product__right__top__infos__price h2 {
    font-family: Mulish;
    font-size: 21px;
    font-weight: 400;
    line-height: 26.36px;
    text-align: left;
    color: rgba(0, 0, 0, 0.5);
    text-decoration: line-through;
}

.section__product__right__top__infos__review p {
    font-family: Mulish;
    font-size: 14px;
    font-weight: 500;
    line-height: 17.57px;
    text-align: left;
    color: rgba(185, 187, 191, 1);

}

.section__product__right__top__infos__review span {
    color: rgba(62, 146, 66, 1);

}

.section__product__right__top__infos__review__item {
    display: flex;
    gap: 12px;
    justify-content: left;

}

.section__product__right__top__infos__review__item div {
    padding: 7px 10px 7px 10px;
    display: flex;
    gap: 7px;
    opacity: 0px;
    border-radius: 27px;
    font-family: Mulish;
    font-size: 14px;
    font-weight: 600;
    line-height: 17.57px;
    text-align: left;
    margin-bottom: 7px;
}

.section__product__right__top__infos__review__rating {
    background: rgba(251, 243, 234, 1);
    color: rgba(212, 141, 59, 1);
}

.section__product__right__top__infos__review__feedback {
    background: rgba(237, 240, 248, 1);
    color: rgba(58, 73, 128, 1);

}

.section__product__right__info h3 {
    font-family: Inter;
    font-size: 16px;
    font-weight: 500;
    line-height: 19.36px;
    text-align: left;
    color: rgba(185, 187, 191, 1);

}

.section__product__right__info__colors--select button {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    opacity: 0px;
    background-color: rgba(238, 238, 238, 1);

}
</style>