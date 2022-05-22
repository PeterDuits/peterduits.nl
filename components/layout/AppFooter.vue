<template>
    <footer class="pd-app-footer">
        <div class="pd-app-footer__social-container">
            <a v-for="(social, i) in socials" :key="i" :href="social.url" target="_blank">
                <div class="pd-app-footer__social-button">
                    <component :is="social.icon" class="pd-app-footer__social-image" role="img" />
                </div>
            </a>
        </div>
        <span class="copyright">© Copyright {{ currentYear }} PeterDuits.nl</span>
    </footer>
</template>

<script>
import LinkedIn from '@/components/icons/LinkedInIcon';
import Instagram from '@/components/icons/InstagramIcon';
import GitHub from '@/components/icons/GitHubIcon';
import GitLab from '@/components/icons/GitLabIcon';

export default {
    name: 'AppFooter',
    data() {
        return {
            socials: [
                {
                    name: 'Instagram',
                    icon: Instagram,
                    url: 'https://www.instagram.com/peterflawless/',
                },
                {
                    name: 'LinkedIn',
                    icon: LinkedIn,
                    url: 'https://www.linkedin.com/in/peter-duits/',
                },
                {
                    name: 'GitLab',
                    icon: GitLab,
                    url: 'https://gitlab.com/Peter_Duits',
                },
                {
                    name: 'GitHub',
                    icon: GitHub,
                    url: 'https://github.com/PeterDuits',
                },
            ],
        };
    },
    computed: {
        currentYear() {
            return new Date().getFullYear();
        },
    },
};
</script>

<style lang="scss">
.pd-app-footer {
    display: flex;
    align-items: center;
    place-content: space-between;
    width: 100%;
    max-width: 1024px;
    padding: 0.8rem 1.5rem;
    margin: 0 auto;
    color: var(--body-1);

    &__social-container {
        display: flex;
    }
    &__social-button {
        display: flex;
        place-items: center;
        margin-right: 10px;
        padding: 10px;
        border-radius: 50%;
        background-color: var(--secondary-color);
        cursor: pointer;
        transition: all 0.5s;

        &:hover {
            box-shadow: var(--secondary-color) 0 1px 20px;
            transition-duration: 0.2s;
        }
    }
    &__social-image {
        height: 20px;
        width: 20px;

        g circle,
        g rect,
        g path,
        path {
            fill: var(--background-1);
        }
    }
}
</style>
