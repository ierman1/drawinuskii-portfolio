<template>
	<div class="view portfolio">
		<lightgallery
            :settings="{ speed: 500, plugins: plugins }"
            :onInit="onInit"
            :onBeforeSlide="onBeforeSlide">
            <a :href="require('@/assets/img/portfolio/portfolio1.jpg')">
                <img alt="Hay que cambiar este texto" src="@/assets/img/portfolio/portfolio1.jpg">
            </a>
            <a :href="require('@/assets/img/portfolio/portfolio2.jpg')">
                <img alt="Hay que cambiar este texto" src="@/assets/img/portfolio/portfolio2.jpg">
            </a>
            <a :href="require('@/assets/img/portfolio/portfolio3.jpg')">
                <img alt="Hay que cambiar este texto" src="@/assets/img/portfolio/portfolio3.jpg">
            </a>
            <a :href="require('@/assets/img/portfolio/portfolio4.jpg')">
                <img alt="Hay que cambiar este texto" src="@/assets/img/portfolio/portfolio4.jpg">
            </a>
            <a :href="require('@/assets/img/portfolio/portfolio5.jpg')">
                <img alt="Hay que cambiar este texto" src="@/assets/img/portfolio/portfolio5.jpg">
            </a>
            <a :href="require('@/assets/img/portfolio/portfolio6.jpg')">
                <img alt="Hay que cambiar este texto" src="@/assets/img/portfolio/portfolio6.jpg">
            </a>
            <a :href="require('@/assets/img/portfolio/portfolio7.jpg')">
                <img alt="Hay que cambiar este texto" src="@/assets/img/portfolio/portfolio7.jpg">
            </a>
            <a :href="require('@/assets/img/portfolio/portfolio8.jpg')">
                <img alt="Hay que cambiar este texto" src="@/assets/img/portfolio/portfolio8.jpg">
            </a>
            <a :href="require('@/assets/img/portfolio/portfolio9.jpg')">
                <img alt="Hay que cambiar este texto" src="@/assets/img/portfolio/portfolio9.jpg">
            </a>
    </lightgallery>
	</div>
</template>

<style lang="scss">

    @import 'lightgallery/css/lightgallery.css';
    @import 'lightgallery/css/lg-thumbnail.css';
    @import 'lightgallery/css/lg-zoom.css';

	.portfolio {
        margin-bottom: 5rem;
        text-align: center;

        @media (min-width: 780px) {
            padding: 2rem;
        }

        img {
            height: 200px;
        }
    }

</style>

<script>

import Lightgallery from 'lightgallery/vue';
import lgThumbnail from 'lightgallery/plugins/thumbnail';
import lgZoom from 'lightgallery/plugins/zoom';

export default {
	name: 'PortfolioView',
	components: {
        Lightgallery
    },
    data: () => ({
        plugins: [lgThumbnail, lgZoom],
    }),
    methods: {
        onInit: () => {
            console.log('lightGallery has been initialized');
        },
        onBeforeSlide: () => {
            console.log('calling before slide');
        },
    },
}

</script>
