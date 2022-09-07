<template>
    <nav class="nav-menu">
		<h1>Drawinuskii</h1>
		<div class="links">
			<router-link to="/">Home</router-link>
			<router-link to="/portfolio">Portfolio</router-link>
			<router-link to="/contact">Contact</router-link>
		</div>
		<div class="socials">
			<a href="https://www.instagram.com/drawinuskii/" title="Instagram" target="_blank">
				<font-awesome-icon icon="fa-brands fa-instagram" size="xl" />
			</a>
			<!--
			<a href="" title="Twitter" target="_blank">
				<font-awesome-icon icon="fa-brands fa-twitter" size="xl" />
			</a>
			-->
			<a href="https://www.artstation.com/davinuskii" title="Artstation" target="_blank">
				<font-awesome-icon icon="fa-brands fa-artstation" size="xl" />
			</a>
		</div>
	</nav>
</template>

<style lang="scss">

	.nav-menu {
		padding: 3rem 2rem;
		text-align: center;

		@media (min-width: 780px) {
			align-items: center;
			display: flex;
		}

		* {
			color: $primary-color;
			font-weight: bold;
		}

		h1 {
			color: $dark-color;
			font-family: 'Secular One', sans-serif;
			font-size: 2rem;
			margin: 0;
			margin-right: auto;
			margin-bottom: 1rem;

			@media (min-width: 780px) {
				margin-bottom: 0;
			}
		}

		.links {
			margin-bottom: 2rem;
			
			@media (min-width: 780px) {
				margin-bottom: 0;
				margin-right: 2rem;
			}

			a {
				font-size: 1.2rem;
				margin-left: 1rem;
				align-items: center;
				text-decoration: none;
				text-transform: uppercase;
				padding-bottom: 5px;
				position: relative;

				&::after {
					background-color: $primary-color;
					content: '';
					display: block;
					height: 1px;
					left: 0;
					position: absolute;
					top: 100%;
					transition: all .2s ease;
					width: 0;
				}

				&:hover::after {
					width: 100%;
				}

				&.router-link-exact-active::after {
					width: 100%;
				}
			}
		}

		.socials {
			a {
				margin: 0 1rem;
			}
		}
	}

</style>