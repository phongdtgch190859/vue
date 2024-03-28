<template>
    <v-container>
        <v-row class="header d-flex  ">
            <v-col class="header_left d-flex">

                <img src="../assets/images/Logo.png" alt="">
                <div class="search-input">
                    <img src="../assets/images/Search.png" alt="Search" class="search-icon">
                    <input type="text" placeholder="Search...">

                </div>

            </v-col>
            <v-col class="header_right ga-4  align-content-center">
                <div class="header_right--icons d-flex ">
                    <img src="../assets/images/Bag2.png" alt="">
                    <img src="../assets/images/Heart.png" alt="">
                </div>
                <button class="outlined">Sign In</button>
                <button class="Tonal">Sign Up</button>
                <div class="header_right-user d-flex">
                    <div class="header_right-user-info">
                        <h3>Name</h3>
                        <span>Description</span>
                    </div>
                    <div class="header_right-user-avatar">
                        <img src="../assets/images/Avatar.png" alt="">
                    </div>
                </div>
                <div class="switch">
                    <img src="../assets/images/Frame1.png" alt="">
                    <div class="switch__top"></div>
                </div>

            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
    name: "TheHeader",
    data() {
        return {
            isDay: true
        };
    },
    methods: {
        toggleDayNight() {
            this.isDay = !this.isDay;
        }
    }
});
</script>
<style>
.header {
    height: 74px;

    margin: 25px 20px;

    justify-content: space-between;
}

.header_left {
    gap: 15px;
    align-items: center;
    width: 30%;
}

.header_left img {
    width: 5.8rem;
    height: 2rem;
}

.search-input {
    position: relative;
    height: 3.5rem;
    display: inline-block;
    display: flex;
    width: 90%;
    align-items: center;
}

.search-input input[type="text"] {
    padding-left: 35px;
    display: inline-block;
    width: 100%;
    height: 100%;
    border: 1px solid #D7D7D7;
    border-radius: 25px;
    /* Để chỗ cho biểu tượng search */
}

.search-input .search-icon {
    position: absolute;
    top: 50%;
    left: 10px;
    transform: translateY(-50%);
    width: 20px;
    height: 20px;
}

.header_right {
    display: flex;
    width: 60%;
    gap: 15px;
    justify-content: end;
    align-items: center;
}

.header_right--icons {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: calc(8% - 15px)
}

.header_right button {
    width: 25%;
    height: 54px;
    border: 1px solid #4e4af2;
    border-radius: 15px;
}

.outlined {
    color: #4e4af2;
}

.Tonal {
    background-color: #4e4af2;
    color: white;

}

.header_right--icons img {
    width: 19px;
    height: 20px;
    display: block;
}

.header_right-user-avatar {
    width: 40%;
    height: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.header_right-user-avatar img {
    width: 50%;
    height: 70%;
}

.header_right-user {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 5px;
    width: 20%;
}

.header_right-user-info span {
    font-size: 12px;
    font-weight: 300;
    line-height: 16px;
}

.header_right-user-info h3 {
    font-size: 12px;
    font-weight: 700;
    line-height: 16px;
}

.switch {
    display: inline-block;
    position: relative;
    margin-top: 5px;

}

.switch img {
    width: 100%;
    height: 100%;

}



.switch__top {
    position: absolute;
    top: -4px;
    right: -4px;
    width: 80%;
    height: 100%;
    background-image: url("../assets/images/Frame2.png");
    background-size: cover;
}
</style>