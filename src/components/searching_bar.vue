<script>
import { stringifyExpression } from '@vue/compiler-core';
import { computed } from '@vue/reactivity';
import axios from 'axios';
import datos from "./events.vue";
export default {
    name: "events",
    props: {
        msg: String
    },
    data(){
        return {
            keyword: '',
            date: '',
            location: '',
            events: ''

        }
    },
    methods: {
        buscarEvents() {
            axios
            .get(`https://app.ticketmaster.com/discovery/v2/events.json?size=1&apikey=${import.meta.env.VITE_KEY}&keyword=${this.keyword}"`)
            .then(response => 
                
                {console.log(response.data)
                this.events= response.data._embedded.events}
            )
        }
 
  }
}

</script>

<template>
    <div id="container-search">
        <p id= "subtitle" for="site-search">What do you feel like doing today?</p>
        <div id="search">
                <div id="input-box">
                    <input type="text" v-model="keyword" class="form-control" placeholder="Key Words">
                    <input type="text" v-model="date" class="search-in-site" placeholder="Date">
                    <input type="text" v-model="location" class="search-in-site" placeholder="Location">
                </div>

                <button id="onclick" @click= "buscarEvents">Let’s go!</button>
            </div>

            <section>
                <div class="each-event" v-for="event in events">
                        <figure>
                            <img class="img-event" v-bind:src="event.images[1].url" alt="">
                        </figure>
                    <div class="event-info">
                        <h3 id= "events-name" >
                            {{ event.name }}
                        </h3>
                        <p>
                            Fecha: {{event.dates.start.localDate}}
                        </p>
                        <a target="_blank" v-bind:href="event.url" >
                            More info
                        </a>
                    </div>
                </div>
            </section>
    </div>

</template>


<style scoped>
    #container-search{
        position: relative;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 20px;  
        justify-content: center;
        padding-left: 85px;
    }

    #search {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
        max-width: 100vw;
    }

    label {
        display: flexbox;
        font:  20px 'Fira Sans', sans-serif;
        width: 100%;
}

    #input-box {
        display: flex;
        flex-direction: row;
        align-items: flex-start;
        padding: 0px;
        width: 100%;
        position: relative;
        gap: 8px;
        box-sizing: border-box;
        flex-wrap: wrap;
}

    input {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        padding: 4px 20px;
        margin: 6px 0px;
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
        gap: 0px;
        width: 100%;
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

    .each-event {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 280px;
        padding: 6px;
    }

    .each-event:hover {
        background-color: #D9D9D7;
    }

    .event-info {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 280px;
        border-color: #000000;
    }

    .img-event {
        width: 230px;
        height: 150px;
        align-items: center;
    }

    h3{
        text-align: center;
        padding: 8px;
        margin: 0 auto;
    }


</style>