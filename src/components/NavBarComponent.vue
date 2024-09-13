<template>
    <div class="navbar">
        <li><router-link to="/emisoraspage" class="router-nav"><strong>EMISORAS</strong></router-link> </li>
        <li><router-link to="/podcastpage" class="router-nav"><strong>PODCAST</strong></router-link> </li>
        <li><router-link to="/milistapage" class="router-nav"><strong>MI LISTA</strong></router-link> </li>
        <li><router-link to="/busquedapage" class="router-nav"><strong>BUSQUEDA</strong></router-link> </li>
    </div>
</template>

<script>
    export default{
        name : 'NavBarComponent'
    }
</script>

<style>
li {
    list-style: none;
    text-decoration: none;
}

.router-nav {
    text-decoration: none;
}

.router-nav:visited, .router-nav:link{
    color: white;
}

.navbar {
    display: flex;
    justify-content: space-around;
    background-color: #202020;
    color: #fff;
    padding: 30px 0px;
}
</style>