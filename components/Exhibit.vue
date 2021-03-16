<template>
    <section :class="`section pb-0 bg-gradient-primary`">
        <div class="container">
            <div v-for="i in Math.ceil(posts.length / 3)" :key="i" class="row row-grid">
                <PostCard
                    v-for="post in posts.slice((i - 1) * 3, i * 3)"
                    :key="post.slug"
                    :prefix="prefix"
                    :post="post"
                    ct="primary"
                ></PostCard>
            </div>
        </div>
    </section>
</template>

<script>
import PostCard from '~/components/PostCard.vue';
export default {
    name: 'Exhibit',
    components: {
        PostCard,
    },
    props: {
        prefix: String,
        slug: String,
        posts: Array,
    },
};
</script>

<style scoped>
.container {
    margin-top: 100px;
    padding-bottom: 100px;
}
</style>
