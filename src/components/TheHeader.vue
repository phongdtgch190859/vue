<!-- eslint-disable vue/no-parsing-error -->
<template>

    <v-row class="header d-flex w-100 justify-space-between align-center">
        <v-col cols="5" class="header-left d-flex align-center">

            <img src="../assets/images/Logo.png" alt="Logo" class="logo"></img>
            <div class="search-input ">

                <v-text-field v-model="search" outlined dense class="search-text-field"><img
                        src="../assets/images/Search.png" alt="Search" class="search-icon"></img>
                    <span>Search...</span>
                </v-text-field>
            </div>
        </v-col>
        <v-col cols="7" class="header-right d-flex ga-4 justify-end align-center">
            <img src="../assets/images/Bag2.png" alt="Bag" class="icon"></img>
            <img src="../assets/images/Heart.png" alt="Heart" class="icon"></img>
            <v-btn class="button d-flex align-center justify-center" color="primary">Sign In</v-btn>
            <v-btn class="button d-flex align-center justify-center outlined">Sign Up</v-btn>
            <div class="header-right-user d-flex align-center ga-5  ">
                <div class="header-right-user-info">
                    <h3>Name</h3>
                    <span>Description</span>
                </div>
                <v-avatar class="header-right-user-avatar">
                    <img src="../assets/images/Avatar.png" alt="Avatar"></img>
                </v-avatar>
            </div>
            <div class="switch">
                <img src="../assets/images/Frame1.png" alt="Switch"></img>
                <div class="switch-top"></div>
            </div>
        </v-col>
    </v-row>

</template>

<script>
export default {
    data() {
        return {
            search: ''
        }
    }
}
</script>

<style scoped>
.header {
    height: 74px;
    margin: 25px 20px;
    position: fixed;
    background-color: white;
    width: 100%;
    margin: 0 auto;
    z-index: 100;
    top: 0;

}

.header-left {
    gap: 15px;
}

.logo {
    width: 5.8rem;
    height: 2rem;
}

.search-text-field {
    width: 345px;
    height: 54px;
    display: flex;
    padding-left: 5px;
    gap: 10px;
    align-items: center;
    border: 1px solid #D7D7D7;
    border-radius: 12px;
    color: #D7D7D7;
}

.search-icon {
    width: 20px;
    height: 20px;
}

.header-right {
    width: 60%;
    gap: 15px;
}

.icon {
    width: 19px;
    height: 20px;
}


.outlined {
    color: #4e4af2;
}

.Tonal {
    background-color: #4e4af2;
    color: white;
}



.header-right-user-avatar {
    width: 40%;
    height: 50%;
}

.header-right-user-avatar img {
    width: 100%;
    height: 70%;
}

.header-right-user-info {
    width: 40%;
}

.header-right-user-info span {
    font-size: 12px;
    font-weight: 300;
    line-height: 16px;
}

.header-right-user-info h3 {
    font-size: 12px;
    font-weight: 700;
    line-height: 16px;
}

.button {
    padding: 19px, 0px, 19px, 0px;
    width: 151px;
    height: 54px;
    border-radius: 12px;
    border: 1px solid #4e4af2;
}

.outlined {
    color: white;
    background-color: #4e4af2;
}

.switch {
    position: relative;
    margin-top: 5px;
}

.switch img {
    width: 100%;
    height: 100%;
}

.switch-top {
    position: absolute;
    top: -4px;
    right: -4px;
    width: 80%;
    height: 100%;
    background-image: url("../assets/images/Frame2.png");
    background-size: cover;
}
</style>