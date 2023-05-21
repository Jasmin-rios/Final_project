<script>
import axios from 'axios';
export default {
    name: "searching_bar",
    data(){},
    methods: {
        searchEvents () {
            axios
            .get()
        },
       
    }
  }

</script>

<template>
    <div id="hero">
        <div id="container-hero">
            <h1>Find what you want to do now</h1><br>
            <h2 for="site-search">What do you feel like doing?</h2><br>
            <div id="input-box">
                    <input type="search" class="search-in-site" placeholder="Key Words">
                    <input type="search" class="search-in-site" placeholder="Date">
                    <input type="search" class="search-in-site" placeholder="Location"><br>
            </div>
                <button id="onclick" >Let’s go!</button>
        </div>
    </div>

</template>


<style>
    #hero{
        background:no-repeat url(../assets/background-image.jpg);
        background-size: cover;
        background-position: center;
        position: relative;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 20px;  
        gap: 10px;
    }

    h1 {
    width: 100%;
    
}
    label {
    display: flexbox;
    font:  20px 'Fira Sans', sans-serif;
    width: 100%;
}

    #input-box {
        text-align: center;
        display: flex;
        flex-direction: row;
        align-items: flex-start;
        padding: 0px;
        gap: 6px;
        width: 100%;
        position: relative;
        padding: 10px 600px 10px 0px;
        gap: 8px;    

}

    input {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        padding: 4px 20px;
        margin: 0px 0px;
        gap: 8px;
        border-radius: 6px;
        background: #FFFFFF;
        border: 1px solid #000000;
        border-radius: 6px;

    }

    #onclick{
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: flex-end;
        padding: 8px 100px;
        gap: 0px;
        width: 625px;
        height: 37px;
        color: #FFFFFF;
        background: #55C8B5;
        border-radius: 8px;
        border: 1px solid #000000;
        font-style: normal;
        font-weight: 600;
        font-size: 14px;
        line-height: 15px;
    }


 

</style>