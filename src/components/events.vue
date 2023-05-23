<script>
    import axios from 'axios';
    export default {
        name: "events",
        data() {
        return{
            events: "",
        }
        },
    mounted () {
        this.showEvents() 
    },
    methods: {
        showEvents(){
            axios
            .get(`https://app.ticketmaster.com/discovery/v2/events.json?classificationName=music&dmaId=324&apikey=${import.meta.env.VITE_KEY}`)
            .then(response => 
                
            {console.log (response)
                this.events= response.data._embedded.events}
                )
            .catch(error=> {
                console.log(error);
        });
        },
        
        }
    }


</script> 

<template>
    <div class="subtitle">
    <h2>Events</h2>
    </div>
    <section class="all_event_cards">
        <div class="each-event" v-for="event in events">
            <figure>
                <img class="img-event" v-bind:src="event.images[1].url" alt="">
            </figure>
            <div class = "event-info">
                <h3 id= "events-name">
                    {{ event.name }}
                </h3>
                <p id="event-id" >

                </p>
                <h5 id="date-id">
                    {{ event.date }}
                </h5>
            </div>
        </div>
    </section>
</template>

<style scoped>
    section {
        display: flex;
        gap: 50px;
        flex-wrap: wrap;
        justify-content: space-around;
        margin: 10px auto;
        align-items: flex-start;
        flex-direction: row;
        width: 90%;
        height: 100%;
        margin: 0 auto;
        box-sizing: border-box;
        padding: 20px;
    }


    section .each-event {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 300px;
        height: 300px;
        transition: bottom 0.3s;
    }

    .each-event .img-event {
        width: 230px;
        height: 165px;
        align-items: center;
    }

    .event-info  {
        margin: 0 auto;
        width: 80%;
        align-items: center;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    h3 {
        font-weight: 700;
        font-size: 18px;
        line-height: 16px;
        text-align: center;
    }

    #event-id {
        font-style: normal;
        font-weight: 400;
        font-size: 16px;
        line-height: 15px;
    }
    
    h2 {
        display: flex;
        flex-direction: row;
        align-items: flex-start;
        padding: 0px 0px 0px 90px;

        width: 146px;
        height: 24px;

    }

</style>