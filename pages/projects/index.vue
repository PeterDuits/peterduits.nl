<template>
    <div>
        <Exhibit prefix="project" :slug="slug" :posts="posts" />
    </div>
</template>

<script>
import Exhibit from '~/components/Exhibit.vue';
export default {
    name: 'Project',
    components: {
        Exhibit,
    },
    props: {
        slug: {
            type: String,
        },
    },
    asyncData() {
        const resolve = require.context('~/posts/', true, /\.md$/);
        const imports = resolve
            .keys()
            .map((key) => {
                const [, slug] = key.match(/\/(.+)\.md$/);
                return Object.assign(resolve(key), { slug });
            })
            .filter((post) => post.attributes.category === 'project');
        return {
            posts: imports,
        };
    },
};
</script>
