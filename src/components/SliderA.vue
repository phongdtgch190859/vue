<template>
    <div class="slideshow-container">
        <div v-for="(slide, index) in slides" :key="index" class="mySlides" :class="{ 'fade': index === slideIndex }">
            <div class="numbertext">{{ index + 1 }} / {{ slides.length }}</div>
            <img :src="slide.image" style="width:100%">
            <div class="text">{{ slide.caption }}</div>
        </div>
        <a class="prev" @click="plusSlides(-1)">&#10094;</a>
        <a class="next" @click="plusSlides(1)">&#10095;</a>
    </div>
    <br>
    <div style="text-align:center">
        <span v-for="(dot, index) in slides" :key="index" class="dot" @click="currentSlide(index)"
            :class="{ 'active': index === slideIndex }"></span>
    </div>
</template>

<script>
export default {
    data() {
        return {
            slideIndex: 0,
            timeoutId: null,
            slides: [
                { image: 'https://www.w3docs.com/uploads/media/default/0001/03/66cf5094908491e69d8187bcf934050a4800b37f.jpeg', caption: 'London, England' },
                { image: 'https://www.w3docs.com/uploads/media/default/0001/03/b7d624354d5fa22e38b0ab1f9b905fb08ccc6a05.jpeg', caption: 'Sunset in Romania' },
                { image: 'https://www.w3docs.com/uploads/media/default/0001/03/5bfad15a7fd24d448a48605baf52655a5bbe5a71.jpeg', caption: 'New York, USA' }
            ]
        };
    },
    mounted() {
        this.showSlides();
    },
    methods: {
        currentSlide(index) {
            this.slideIndex = index;
            this.showSlides();
        },
        plusSlides(step) {
            this.slideIndex += step;
            if (this.slideIndex >= this.slides.length) {
                this.slideIndex = 0;
            } else if (this.slideIndex < 0) {
                this.slideIndex = this.slides.length - 1;
            }
            this.showSlides();
        },
        showSlides() {
            clearTimeout(this.timeoutId);
            this.slides.forEach((slide, index) => {
                slide.style.opacity = index === this.slideIndex ? "1" : "0";
            });
            this.timeoutId = setTimeout(this.showSlides, 5000); // Change image every 5 seconds
        }
    }
};
</script>

<style>
.slideshow-container {
    max-width: 1000px;
    position: relative;
    margin: auto;
}

.mySlides {
    display: none;
    position: absolute;
    transition: opacity 1.5s ease;
}

.fade {
    opacity: 1;
}

.prev,
.next {
    cursor: pointer;
    position: absolute;
    top: 50%;
    width: auto;
    padding: 16px;
    margin-top: -22px;
    color: white;
    font-weight: bold;
    font-size: 18px;
    transition: 0.6s ease;
    border-radius: 0 3px 3px 0;
    user-select: none;
}

.prev {
    left: 0;
    border-radius: 3px 0 0 3px;
}

.next {
    right: 0;
    border-radius: 3px 0 0 3px;
}

.prev:hover,
.next:hover {
    background-color: rgba(0, 0, 0, 0.8);
}

.text {
    color: #ffffff;
    font-size: 15px;
    padding: 8px 12px;
    position: absolute;
    bottom: 8px;
    width: 100%;
    text-align: center;
}

.numbertext {
    color: #ffffff;
    font-size: 12px;
    padding: 8px 12px;
    position: absolute;
    top: 0;
}

.dot {
    cursor: pointer;
    height: 15px;
    width: 15px;
    margin: 0 2px;
    background-color: #999999;
    border-radius: 50%;
    display: inline-block;
    transition: background-color 0.6s ease;
}

.active,
.dot:hover {
    background-color: #111111;
}

@media only screen and (max-width: 300px) {

    .prev,
    .next,
    .text {
        font-size: 11px;
    }
}
</style>