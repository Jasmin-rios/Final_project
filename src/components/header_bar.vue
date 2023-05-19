<script>
import axios from 'axios'
export default {
    name: "header_bar",
    methods:{ 
    infoAPI(){
        console.log(import.meta.env.VITE_KEY)
        axios
        .get(`https://app.ticketmaster.com/discovery/v2/events.json?apikey=${import.meta.env.VITE_KEY}&city=Madrid`)
        .then(response => console.log(response.data))
    }}
}




</script>

<template>

    <header>
        <img id="logo" src="../assets/Logo.png" @click="infoAPI">
        <div id="button-container">
            <button class="header_bar">Log In</button>
            <button class="header_bar">Sign Up</button>
        </div>      
    </header><br>    

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
    padding: 20px 0 0 0;
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
    }


</style>
