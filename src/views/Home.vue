<template>
    <div>
        <h2>PLAN WITH ME</h2>
        <p>Hi! I was created to help You not forget about Your plans! </p>
        <p>Hope, You will enjoy planing different stuff with me :)</p>
        <router-link to="/todos">
            <img src="https://pngimg.com/uploads/banana/banana_PNG838.png">
        </router-link>
    </div>
</template>

<script>
    export default {
        name: "Home"
    }

</script>

<style>
    img{
        max-width: 90px;
        max-height: 90px;
    }
</style>