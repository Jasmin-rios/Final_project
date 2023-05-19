<script>
export default {
    name: "searching_bar",
    methods: {
        function (mensaje) {
        alert(mensaje)
    }
  }
}

</script>

<template>
    <!-- <img id= "background-image" src="../assets/imagen_central.jpg"/> -->
    <div id="image-search-bar">
        <h1>Find what you want to do now</h1><br>
        <label for="site-search">What do you feel like doing?</label><br>
        <div id="input-box">
            <input type="search" class="search-in-site" placeholder="Key Words">
            <input type="search" class="search-in-site" placeholder="Date">
            <input type="search" class="search-in-site" placeholder="Location"><br>
        </div>
        <button id="onclick">Let’s go!</button>
    </div>
</template>


<style>
    #image-search-bar{
        background:no-repeat url(../assets/imagen_central.jpg);
        position: relative;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 20px;  
        gap: 10px;
}
    label {
    display: flexbox;
    font:  20px 'Fira Sans', sans-serif;
}

input {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 4px 24px;
    gap: 8px;
}

#input-box {
    text-align: center;
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    padding: 0px;
    gap: 11px;

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

#background-image {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 30px;
    position: relative;
    width: 100%;
    height: 270px;

}



</style>