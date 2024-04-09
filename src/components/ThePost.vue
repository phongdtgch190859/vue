<template>

    <div class="post" v-show="post.isVisible">
        <div class="post__content">
            <h3>{{ post.content }}</h3>
            <a href="#">Read more</a>
        </div>
        <div class="post__image">
            <img src="../assets/images/imagePost.png" alt="">
        </div>
    </div>


</template>

<script>
import { defineComponent } from "vue";
export default defineComponent({
    name: "ThePost",
    props: {
        post: {

            type: Object,
            required: true
        }
    }
});
</script>
<style scoped>
.post {
    width: 370px;
    height: 270px;
    font-family: Mulish;
    text-align: left;
    font-weight: 600;
    background: rgba(238, 239, 251, 1);
    box-sizing: border-box;
    position: relative;
}

.post h3 {
    font-size: 26px;
    line-height: 32.63px;
    color: rgba(21, 24, 117, 1);
}

.post a {
    font-size: 16px;
    line-height: 20.08px;
    color: rgba(78, 74, 242, 1);
}

.post__content {
    padding-top: 22px;
    padding-left: 20px;
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.post__image {
    width: 274px;
    height: 173px;
    object-fit: cover;
    position: absolute;
    bottom: 0;
    right: 0;
}
</style>