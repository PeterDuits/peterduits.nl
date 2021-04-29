<template>
    <div class="default-container">
        <div class="default-container__inner">
            <AppHeader />
            <Nuxt />
        </div>
    </div>
</template>

<script>
import AppHeader from '../components/layout/AppHeader';
export default {
    name: 'DefaultLayout',
    components: { AppHeader },
};
</script>

<style lang="scss">
.default-container {
    height: 200vh;
    background-color: #151515;

    &__inner {
        height: 200vh;
        background-image: url('~assets/images/blob-#{random(4)}.svg'), url('~assets/images/blob-#{random(4)}.svg'),
            url('~assets/images/blob-#{random(4)}.svg'), url('~assets/images/blob-#{random(4)}.svg');
        background-repeat: no-repeat;
        background-position: 5vw -5vw, 55vw 20vw, 5vw 45vw, 55vw 70vw;
        background-size: 40vw;
        opacity: 0.8;
    }
}
</style>
