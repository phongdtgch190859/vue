<template>
    <div class="container__category">
        <div class="section">
            <div class="title">
                <h1>CATEGORY</h1>
            </div>
            <div class="options">
                <ul>
                    <li><a href="#"></a>New Arrival</li>
                    <li><a href="#"></a>Best Selle</li>
                    <li><a href="#"></a>Featured</li>
                    <li><a href="#"></a>Special Offer</li>
                    <li><a href="#"></a>More</li>
                </ul>
            </div>
            <div class="category-data">
                <TheCart v-for="(card, index) in features" :key="index" :card="card">
                </TheCart>
            </div>

        </div>
        <div class="load" v-show="!isActive">
            <button @click="loadMore()">Load More</button>
        </div>
        <div>
            <p v-show="isActive" @click="showLess()">show less</p>
        </div>
    </div>
</template>

<script>
import { defineComponent, ref } from "vue";
import TheCart from "./TheCart.vue";
export default defineComponent({
    name: "TheCategory",
    components: {
        TheCart,
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
.container__category {
    position: relative;
}


.section {
    position: relative;
    width: 100%;
    margin: 0 auto;
    padding: 32px 117px;
    margin-top: 32px;
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

.options {
    margin: 39px 0px 39px 0px;
}

.options ul {

    display: flex;
    align-items: center;
    justify-content: center;
    text-decoration: none;
    gap: 50px;
    list-style-type: none;
    font-family: Lato;
    font-size: 18px;
    font-weight: 400;
    line-height: 21.6px;
    text-align: left;
    color: rgba(21, 24, 117, 1);

}


.options ul>li:first-child {
    color: rgba(78, 74, 242, 1);
    line-height: 2.59px;
    text-decoration: underline;
    text-underline-offset: 3px;
}

.options ul>li:hover {
    color: rgba(78, 74, 242, 1);
    text-decoration: underline;
}




.category-data {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    align-items: center;
    gap: 30px;
    margin-top: 30px;

}

.load {
    position: absolute;
    bottom: 0;
    display: flex;
    justify-content: center;
    align-items: end;
    background: linear-gradient(180deg, rgba(255, 255, 255, 0) 0%, rgba(251, 251, 251, 0.8) 44.79%, #FFFFFF 100%);
    width: 100%;
    height: 400px;
    left: 50%;
    /* Di chuyển phần tử lên 50% theo chiều ngang */
    transform: translateX(-50%);
}

.load>button {
    display: inline-block;
    width: 164px;
    height: 65px;
    color: white;
    border-radius: 18px;
    border: 1px solid rgba(78, 74, 242, 1);
    background: rgba(107, 104, 252, 1);
    margin-bottom: 10px;
    position: relative;
    cursor: pointer;
}
</style>