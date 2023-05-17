<script>
export default {
    name: "searching_bar",
}

</script>

<template>
<!--     <h2>
        What do you feel like doing?
    </h2>
    <input placeholder="Search key word"/>
    <button>Let’s go!</button> -->
    <label for="site-search">What do you feel like doing?</label><br>
    <input type="search" id="site-search">
    <input type="search" id="site-search">
    <input type="search" id="site-search">
    <button>Let’s go!</button>
</template>


<style>
    label {
    display: flexbox;
    font: 1rem 'Fira Sans', sans-serif;
}

input,
label {
    display: flexbox;
    display: inline-block;
    margin: 0.4rem 0;
}


</style>