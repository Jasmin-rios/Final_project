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
        <div id="search">
                <div id="input-box">
                    <input type="text" v-model="keyword" class="form-control" placeholder="Key Words">
                    <input type="search" v-model="date" class="search-in-site" placeholder="Date">
                    <input type="search" v-model="location" class="search-in-site" placeholder="Location"><br>
                </div>
                    <button id="onclick" @click= "buscarEvents">Let’s go!</button>
            </div>

            <section>
                <div class="each-event" v-for="event in events">
                    <figure>
                        <img class="img-event" v-bind:src="events" alt="">
                    </figure>

                    <div class = "event-info">
                        <h3 id= "events-name" >
                            {{ event.name }}
                        </h3>
                        <p>
                            Fecha: {{event.dates.start.localDate}}
                        </p>
                        <a v-bind:href="event.url">
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
        padding: 16px;  
        gap: 10px;
        justify-content: center;
        
    }

    #search {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
        padding: 0px;
        opacity: 1;
        max-width: 100vw;
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