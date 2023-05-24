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
    
    <div id="hero">
        <h1>Find what you want to do now</h1><br>
        <p id= "subtitle" for="site-search">What do you feel like doing?</p><br>
    </div> 

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
        font-size: 36px;
        font-weight: 300;
        background-color: #CEF8F1;
        max-width: max-content;
        outline-color: white;
    
}
    #hero {
        background:no-repeat url(../assets/background-image_2.jpg);
        background-size: cover;
        background-position: center;
        width: 100%;
        opacity: 1;
        padding: 20px;
        fill-opacity: 0.5;
    }

</style>
