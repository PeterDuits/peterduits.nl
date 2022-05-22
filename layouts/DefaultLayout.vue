<template>
    <div>
        <AppHeader />
        <Nuxt />
        <AppFooter />
    </div>
</template>

<script>
import AppHeader from '~/components/layout/AppHeader';
import AppFooter from '@/components/layout/AppFooter';

export default {
    name: 'DefaultLayout',
    components: { AppFooter, AppHeader },
};
</script>
