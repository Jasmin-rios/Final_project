<script>
import axios from 'axios'
export default {
    name: "header_bar",
    methods:{ 
    infoAPI(){
        // console.log(import.meta.env.VITE_KEY)
        axios
        .get(`https://app.ticketmaster.com/discovery/v2/events.json?apikey=${import.meta.env.VITE_KEY}&city=Madrid`)
        .then(response => console.log(response.data))
    }}
}

</script>

<template>
    <header>
        <img id="logo" src="../assets/logo_mejorado.svg" >
        <div id="button-container">
            <button class="header_bar">Log In</button>
            <button class="header_bar">Sign Up</button>
        </div>      
    </header><br>   
    <section class="container-hero">
        <div id="hero">
            <h1>Find what you want to do now</h1><br>
        </div>
    </section>
</template>

<style>

    .wrapper {
        width: 95%;
        max-width: 1000px;
        margin: auto;
        overflow: hidden;
    }
   header {
    display: flex;
    flex-direction:row;
    align-items: flex-start;
    padding: 0px 0 0 0;
    gap: auto;
    margin: 0;
    justify-content: space-between;
    align-items: center;
    width: 100%;

   }
   #logo{
    position: relative;
    font-weight: bold;
    font-size: 2em;
    letter-spacing: 2px;
    text-decoration: none;
    width: 166.5px;
   }

    button {
        font-size: 14px;
        border: solid 0.5px #000;
        background-color: #DAEBFB;;
        border-color: #DAEBFB;;
        padding: 8px 16px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        display: flexbox;
        font-size: 12px;
        margin: 4px 2px;
        cursor: pointer;
        border-radius: 8px;
        font-style: normal;
        line-height: 17px;
        color: #000000;
        border: 1px solid #000000;

    } 
    h1 {
        color: black;
        text-shadow:
        -1px -1px 0 #eee,
        1px -1px 0 #eee,
        -1px 1px 0 #eee,
        1px 1px 0 #eee;
        /* background: black;       */
        font-size: 36px;
}
    
    #hero {
        background:no-repeat url(../assets/background-image_2.jpg);
        background-size: cover;
        background-position: 0px -200px;
        opacity: 0.9;
        padding: 90px 40px;
        width: 90%;
        align-items: center;
        margin: 0 auto;
    }
    .container-hero {
        align-items: center;
    }
</style>
