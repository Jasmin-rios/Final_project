<script>
import axios from 'axios';
export default {
    name: "searching_bar",
    data() {
        return{
            events: "",
            favoriteEvents: [],
        }
        },
    methods: {
        searchEvents(){
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
    <div id="searching-bar">
        <h1>Find what you want to do now</h1><br>
        
            <label for="site-search">What do you feel like doing?</label><br>
            <div id="input-box">
                <input type="search" class="search-in-site" placeholder="Key Words">
                <input type="search" class="search-in-site" placeholder="Date">
                <input type="search" class="search-in-site" placeholder="Location"><br>
            </div>
            <button id="onclick" @click="searchEvents">Let’s go!</button>
        
    </div>

    <div v-for="event in events">
        <div class="event-name">
        {{ event.name }}
        </div>
        <div class="event-id">
        {{ event.id }}
        </div>
    </div>
</template>


<style>
    #searching-bar{
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
        gap: 10x;
        width: 100%;

}

input {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 4px 24px;
    gap: 8px;
    
}


#onclick{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: flex-end;
    padding: 10px 100px;
    gap: 8px;
    width: 723px;
    height: 37px;
    background: #D79A9A;
    border-radius: 8px;
    color: #FFFFFF;
    border: #D79A9A;
}


</style>