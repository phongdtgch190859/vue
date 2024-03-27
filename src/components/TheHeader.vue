<template>
    <v-container>
        <v-row class="header d-flex  ">
            <v-col class="header_left w-50 d-flex">

                <img src="../assets/images/Logo.png" alt="">
                <div class="search-input">
                    <img src="../assets/images/Search.png" alt="Search" class="search-icon">
                    <input type="text" placeholder="Search...">

                </div>

            </v-col>
            <v-col class="header_right w-50  ga-4  align-content-center">
                <div class="header_right--icons d-flex ">
                    <img src="../assets/images/Bag2.png" alt="">
                    <img src="../assets/images/Heart.png" alt="">
                </div>
                <button class="outlined">Sign In</button>
                <button class="Tonal">Sign Up</button>
                <div class="header_right-user d-flex">
                    <div class="header_right-user-info  ">
                        <p>Name</p>
                        <p>Description</p>
                    </div>
                    <img src="../assets/images/Avatar.png" alt="">
                </div>
                <div class="switch">
                    <input type="checkbox" id="dayNightSwitch" v-model="isNight" @change="toggleDayNight">
                    <label class="switch-background" for="dayNightSwitch">
                        <img src="../assets/images/Frame1.png" alt="">
                        <div class="switch-button" :class="{ 'night': !isDay }">
                            <img src="../assets/images/Frame2.png" alt="">
                        </div>
                    </label>
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
    height: 4.6rem;
    padding: 0.6rem;
    margin: 0 auto;
}

.header_left {
    gap: 15px;
    align-items: center;
}

.header_left img {
    width: 5.8rem;
    height: 2rem;
}

.search-input {
    position: relative;
    height: 3.5rem;
    width: 60%;
    display: flex;
    border: 1px solid #D7D7D7;
    border-radius: 25px;
}

.search-input input[type="text"] {
    padding-left: 35px;
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
    margin: 0 auto;
    gap: 15px;
    justify-content: flex-end;
}

.header_right--icons {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: calc(10% - 15px)
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

.switch {
    display: inline-block;
    position: relative;

}

.switch input[type="checkbox"] {
    display: none;
}

.switch .switch-background {
    position: relative;
    display: block;
    width: 100%;
    /* Kích thước của phần nền */
    height: 100%;
    /* Kích thước của phần nền */
}

.switch .switch-background img {
    width: 50%;
    height: 100%;
}

.switch .switch-button {
    position: absolute;
    top: 0;
    right: 0;
    width: 70%;
    /* Kích thước của phần switch */
    height: 100%;
    /* Kích thước của phần switch */
    transition: transform 0.3s ease;
}

.switch .switch-button img {
    width: 100%;
    height: 100%;
}

.switch .switch-button.night {
    transform: translateX(50px);
    /* Di chuyển phần switch sang phải */
}
</style>