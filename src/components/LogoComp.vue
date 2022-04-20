<template>
    <img src="../assets/img/logo-small.svg" alt="Spotify Logo">
</template>

<script>
export default {
    name: 'LogoComp',
}
</script>

<style lang="scss" scoped>
    img {
        height: 50px;
        padding: 10px;
        filter: invert(54%) sepia(69%) saturate(517%) hue-rotate(89deg) brightness(107%) contrast(95%);
        z-index: 1;
    }
</style>