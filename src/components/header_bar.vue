<script>
import axios from 'axios'
export default {
    name: "header_bar",
    methods:{ 
    infoAPI(){
        axios
    .get('https://app.ticketmaster.com/discovery/v2/events/k7vGFKzleBdwS/images.json?apikey={apikey}')
      .then(response => console.log(response.data))
    }}
}

</script>

<template>

    <header>
        <img id="logo" src="../assets/logo-social.png" @click="infoAPI">
        <div id="button-container">
            <button class="header_bar1">Log In</button>
            <button class="header_bar2">Sign Up</button>
        </div>      
    </header><br>
        
    <h1>Find what you want to do now</h1><br>
    

</template>

<style>
   header {
    display: flex;
    flex-direction:row;
    align-items: flex-start;
    padding: 0px;
    gap: auto;
    margin: 0;
    justify-content: space-between;
    align-items: center;
    width: 100%;
   }
   header img{
    height: 100px;
    position: relative;
    font-weight: bold;
    font-size: 2em;
    letter-spacing: 2px;
    text-decoration: none;
   }

  /*  header button-container{
    position: absolute;
    top: 10px;
    right: 10px;
    display: inline-block;
   } */


     button {
        font-size: 14px;
        border: solid 0.5px #000;
        background-color: cornflowerblue;
        padding: 10px 30px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        display: flexbox;
        font-size: 12px;
        margin: 4px 2px;
        cursor: pointer;
          
    } 
    h1 {
        font-size: 36px;
    }


</style>
