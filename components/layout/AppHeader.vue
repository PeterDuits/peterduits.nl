<template>
    <header>
        <nav class="pd-main-nav">
            <img :src="mainLogo" class="pd-main-nav__logo" alt="Main Logo" />
            <span class="pd-main-nav__logo-text">Peter Duits</span>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'AppHeader',
    data() {
        return {
            mainLogo: require('~/assets/images/pd.svg'),
        };
    },
};
</script>

<style lang="scss" scoped>
.pd-main-nav {
    display: flex;
    align-items: center;
    width: 100%;
    max-width: 1024px;
    padding: 0.6rem 1.5rem;
    margin: 0 auto;
    color: var(--body-1);

    &__logo {
        height: 40px;
        width: auto;
    }

    &__logo-text {
        padding: 0 12px;
        font-size: 2rem;
        font-weight: 600;
    }
}
</style>
