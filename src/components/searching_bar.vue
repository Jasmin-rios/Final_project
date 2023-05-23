<script>
import { stringifyExpression } from '@vue/compiler-core';
import { computed } from '@vue/reactivity';
import axios from 'axios';
import datos from "./events.vue"
export default {
    name: "searching_bar",
    name: "Eventos-extraídos",
    methods: {
        searchEvents () {
            axios
            .get()
        },
    props: {
        msg: String
    },
    data(){
        return {
            buscar: ''
        }
    },
    },
    computed: {
        items () {
            return datos.filter(item => {
                return item.nombre.toLowerCase().includes(this.buscar.toLowerCase());
            });
        },
    }
  }

</script>

<template>
    <div id="aquí-img">
        <div id="hero">
            <div id="container-hero">
                <h1>Find what you want to do now</h1><br>
                <p id= "subtitle" for="site-search">What do you feel like doing?</p><br>
                <div id="input-box">
                        <input type="search" v-model= "buscar" class="search-in-site" placeholder="Key Words">
                        <input type="search" class="search-in-site" placeholder="Date">
                        <input type="search" class="search-in-site" placeholder="Location"><br>
                </div>
                    <button id="onclick" >Let’s go!</button>
            </div>
        </div>
    </div>

</template>


<style scoped>
    #hero{
        /* background:no-repeat url(../assets/background-image_2.jpg);
        background-size: cover;
        background-position: center; */
        position: relative;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 16px;  
        gap: 10px;
        justify-content: center;
        
    }

    #container-hero {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
        padding: 0px;
        opacity: 1;
    }
    #aquí-img {
        background:no-repeat url(../assets/background-image_2.jpg);
        background-size: cover;
        background-position: center;
        width: 100%;
        opacity: 0.9;
    }

    h1 {
    width: 100%;
    outline-color: 5px green;

    
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
        box-sizing: border-box;
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
        box-sizing: border-box;
        outline: none;
    }

    
    #subtitle {
        font-style: normal;
        font-weight: 600;
        font-size: 20px;
        line-height: 24px;

        color: #000000;
    }

</style>