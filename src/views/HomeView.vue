<template>
	<div class="view home">
		<div class="banner">
			<h2>Davinia F. Duport</h2>
			<p class="intro">
				Animation student based in Madrid, Spain. <br><br>
				Digital and traditional artist specialized in storyboard, character design, illustration and concept art. <br><br>
				Experience with 3D and 2D animation.
			</p>
		</div>

		<div class="gallery">
			<h2>Some of my work</h2>

			<div class="glide">
				<div class="glide__track" data-glide-el="track">
					<ul class="glide__slides">
						<li class="glide__slide">
							<img src="@/assets/img/home/home1.jpg" alt="">
						</li>
						<li class="glide__slide">
							<img src="@/assets/img/home/home2.jpg" alt="">
						</li>
						<li class="glide__slide">
							<img src="@/assets/img/home/home3.jpg" alt="">
						</li>
						<li class="glide__slide">
							<img src="@/assets/img/home/home4.jpg" alt="">
						</li>
						<li class="glide__slide">
							<img src="@/assets/img/home/home5.jpg" alt="">
						</li>
					</ul>
				</div>
				<div class="glide__arrows" data-glide-el="controls">
					<button class="glide__arrow glide__arrow--left" data-glide-dir="<">
						<font-awesome-icon icon="fa-solid fa-arrow-left" />
					</button>
					<button class="glide__arrow glide__arrow--right" data-glide-dir=">">
						<font-awesome-icon icon="fa-solid fa-arrow-right" />
					</button>
				</div>
				<div class="glide__bullets" data-glide-el="controls[nav]">
					<button class="glide__bullet" data-glide-dir="=0"></button>
					<button class="glide__bullet" data-glide-dir="=1"></button>
					<button class="glide__bullet" data-glide-dir="=2"></button>
					<button class="glide__bullet" data-glide-dir="=3"></button>
					<button class="glide__bullet" data-glide-dir="=4"></button>
				</div>
			</div>

		</div>
	</div>
</template>

<style lang="scss">

	// Required Core Stylesheet
	@import "node_modules/@glidejs/glide/src/assets/sass/glide.core";

	// Optional Theme Stylesheet
	@import "node_modules/@glidejs/glide/src/assets/sass/glide.theme";

	.home {
		.banner {
			align-items: center;
			background-color: $primary-color;
			display: flex;
			flex-direction: column;
			margin-bottom: 5rem;
			opacity: 80%;
			padding: 1rem 3rem;
			text-align: center;

			@media (min-width: 800px) {
				padding: 5rem 3rem;
			}

			* {
				color: $light-color;
			}

			h2 {
				font-size: 2rem;
				font-weight: bold;
			}

			p {
				font-size: 1.1rem;
				line-height: 1.5rem;
				letter-spacing: .1rem;
				text-transform: uppercase;

				@media (min-width: 800px) {
					width: 600px;
				}
			}
		}

		.gallery {
			text-align: center;
			margin-bottom: 5rem;

			h2 {
				color: $primary-color;
				font-size: 2rem;
				font-weight: bold;
				margin: 0;
				margin-bottom: 3rem;
			}

			img {
				height: 300px;

				@media (min-width: 800px) {
					height: 600px;
				}
			}

			.glide__arrow {
				border-radius: 50%;
				
				svg path {
					fill: $light-color;
				}

				@media (max-width: 1200px) {
					background-color: $primary-color;
					border-color: $light-color;

					svg path {
						fill: $light-color;
					}
				}
			}
		}
	}

</style>

<script>

import Glide from '@glidejs/glide'

export default {
	name: 'HomeView',
	components: {},
	mounted() {
		new Glide('.glide', {
			type: 'carousel',
			perView: 3,
			focusAt: 'center',
			breakpoints: {
				1850: {
					perView: 2
				},
				1200: {
					perView: 1
				}
			}
		}).mount()
	}
}

</script>
