<template>
    <div class="container__trending">
        <div class="section">
            <div class="title">
                <h1>TRENDING</h1>
            </div>
            <div class="section__bottom">
                <div class="section__bottom__left">
                    <div class="section__bottom__left__eclip">
                    </div>
                    <div class="section__bottom__left__good">
                        <img src="../assets/images/trending.png" alt="">
                    </div>
                    <div class="section__bottom__left__content">
                        <h2>Get Up to 30% Off</h2>
                        <p>You can get 30% off this product
                            if you are buying now</p>
                    </div>
                </div>
                <div class="section__bottom__right">
                    <h3>Purchase your <br>
                        <a href="">shoes</a> now.
                    </h3>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Dolor morbi velit turpis et dolor sit
                        morbi odio id. Aliquam ultricies tortor ac.</p>
                    <button>Buy now</button>
                </div>
            </div>

        </div>
    </div>
</template>

<script>
import { defineComponent, ref } from "vue";
export default defineComponent({
    name: "TheTrending",
    components: {
    },
    data() {
        return {
            isActive: false,
            length: 12,
            features: [
                {
                    isVisible: false,
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
                    isVisible: false,
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
                {
                    isVisible: false,
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
                    isVisible: false,
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
                    isVisible: false,
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
    mounted() {
        this.showSlides(this.length);
    },
    methods: {
        showLess() {
            this.isActive = false;
            this.showSlides(this.length);
        },

        loadMore() {
            this.isActive = true;
            this.showSlides(this.features.length);
        },

        showSlides(length) {
            for (let i = 0; i < length; i++) {
                this.features[i].isVisible = true;
            }
        }



    }
});
</script>

<style scoped>
.container__trending {
    background-color: rgba(241, 240, 255, 1);
}


.section {
    position: relative;
    width: 80%;
    margin: 0 auto;

    margin-top: 64px;
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

.section__bottom__left {
    position: relative;
}

.section__bottom__left__good {
    width: 577px;
    height: 505px;
    object-fit: cover;
    position: absolute;
    top: -80px;
    left: -30px;
}

.section__bottom__left__eclip {
    width: 481px;
    height: 449px;
    border-radius: 41% 59% 38% 62% / 53% 53% 47% 47%;
    background-color: rgba(245, 225, 252, 1);
}

.section__bottom__left__content {
    position: absolute;
    width: 240px;
    height: 103px;
    box-sizing: border-box;
    padding: 17px 20px;

    z-index: 100;

    top: 40px;
    left: -70px;
    backdrop-filter: blur(8px);

}

.section__bottom__left__content::before {
    content: "";
    position: absolute;
    inset: 0;
    padding: 1px;
    border-radius: 10px;
    background: linear-gradient(144.76deg, rgba(166, 20, 115, 0.78) -0.67%, #FFFFFF 43.53%, rgba(5, 242, 242, 0.94) 88.65%);
    -webkit-mask:
        linear-gradient(#fff 0 0) content-box,
        linear-gradient(#fff 0 0);
    -webkit-mask-composite: xor;
    mask-composite: exclude;
}

.section__bottom__left__content h2 {
    font-family: Lato;
    font-size: 16px;
    font-weight: 900;
    line-height: 19.2px;
    text-align: left;
}

.section__bottom__left__content p {
    padding-top: 10px;
    font-family: Lato;
    font-size: 14px;
    font-weight: 400;
    line-height: 20px;
    text-align: left;

}

.section__bottom {
    padding-top: 64px;
    display: flex;

    gap: 12%;
}

.section__bottom__right h3,
a {
    color: rgba(78, 74, 242, 1);
    font-family: Mulish;
    font-size: 56px;
    font-weight: 900;
    line-height: 76.5px;
    text-align: left;

}

.section__bottom__right p {
    display: block;
    font-family: Mulish;
    font-size: 18px;
    font-weight: 400;
    line-height: 38px;
    text-align: left;
    color: rgba(0, 0, 0, 1);
    margin-top: 30px;


}

.section__bottom__right button {
    display: block;
    background: rgba(255, 255, 255, 1);
    color: rgba(78, 74, 242, 1);
    box-shadow: 2px 11px 20px 0px rgba(51, 99, 108, 0.08);
    border-radius: 10px;
    padding: 20px 50px;
    margin-top: 60px;
    font-family: Mulish;
    font-size: 24px;
    font-weight: 500;
    line-height: 30.12px;
    text-align: left;
}

.section__bottom__right {
    width: 50%;
}
</style>