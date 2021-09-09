<template>
    <header class="fixed-top primary_color p-2">
        <img src="@/assets/img/logo.png" alt="Spotify Logo">
    </header>
</template>

<script>
export default {
name: 'Header'
}
</script>

<style lang="scss">
@import "@/assets/style/index.scss";
header {
    img {
        height: 50px;
    }
}
</style>