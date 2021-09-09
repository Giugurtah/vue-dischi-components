<template>
    <div class="primary_color text-center h-100 p-2">
        <img :src="album.poster" alt="poster album" class="img-fluid my-3">
        <h4 class="color_text mb-3">{{ album.title.toUpperCase() }}</h4>
        <address class="second_color_text my-0 lh-sm">{{ album.author }}</address>
        <time class="second_color_text lh-sm ">{{ album.year }}</time>
    </div>
</template>

<script>
export default {
name: 'Album',
props: ['album'],
}
</script>

<style lang="scss">
.color_gray {
    color: rgb(100, 105, 109);
}
.color_white {
    color: white;
}
</style>