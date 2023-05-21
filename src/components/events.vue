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
            .get(`https://app.ticketmaster.com/discovery/v2/events.json?apikey=${import.meta.env.VITE_KEY}`)
            .then(response => 
                this.events= response.data._embedded.events)
            .catch(error=> {
                console.log(error);
        });
        },
    }
}

</script> 

<template>
    <section class="all_event_cards">
        <div class="each-event" v-for="event in events">
            <figure class="img-event">

            </figure>
            <div class = "event-info">
                {{ event.status }}
                <h3 id= "events-name">
                    {{ event.name }}
                </h3>
                <p id="event-id">
                    {{ event.id }}
                </p>
            </div>
        </div>
    </section>
</template>

<style>
    section {
        display: flex;
        gap: 10px;
        flex-wrap: wrap;
        justify-content: space-around;
        margin: 0 auto;
    }

    section .each-event {
        
        display: flex;
        flex-direction: column;
        align-items: flex-start;
       
    }

    section .each-event .img-event {
       
    }

</style>