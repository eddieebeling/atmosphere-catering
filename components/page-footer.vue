<template>
	<div class="page-footer">
		<span>Copyright &copy; {{ currentYear }} Atmosphere Catering, LLC. - All Rights Reserved.</span>
		<ul id="social" class="page-footer__social">
			<li class="page-footer__social--item">
				<a href="https://www.instagram.com/atmospherecatering/" target="_blank" rel="noopener noreferrer"
					class="page-footer__social--link"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
						<path
							d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"
							fill="currentColor" />
					</svg></a>
			</li>
			<li class="page-footer__social--item">
				<a href="https://www.facebook.com/atmocatering/" target="_blank" rel="noopener noreferrer"
					class="page-footer__social--link"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512">
						<path
							d="M80 299.3V512H196V299.3h86.5l18-97.8H196V166.9c0-51.7 20.3-71.5 72.7-71.5c16.3 0 29.4 .4 37 1.2V7.9C291.4 4 256.4 0 236.2 0C129.3 0 80 50.5 80 159.4v42.1H14v97.8H80z"
							fill="currentColor" />
					</svg></a>
			</li>
			<li class="page-footer__social--item">
				<a href="https://www.linkedin.com/in/justinpalicki/" target="_blank" rel="noopener noreferrer"
					class="page-footer__social--link"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
						<path
							d="M100.3 448H7.4V148.9h92.9zM53.8 108.1C24.1 108.1 0 83.5 0 53.8a53.8 53.8 0 0 1 107.6 0c0 29.7-24.1 54.3-53.8 54.3zM447.9 448h-92.7V302.4c0-34.7-.7-79.2-48.3-79.2-48.3 0-55.7 37.7-55.7 76.7V448h-92.8V148.9h89.1v40.8h1.3c12.4-23.5 42.7-48.3 87.9-48.3 94 0 111.3 61.9 111.3 142.3V448z"
							fill="currentColor" />
					</svg></a>
			</li>
		</ul>
	</div>
</template>

<script setup>
const currentYear = ref(new Date().getFullYear());
</script>

<style lang="scss">
@use "@/assets/scss/variables.scss" as *;

.page-footer {
	font-size: 0.9375rem;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
	color: rgba(255, 255, 255, 0.5);
	border-top: solid 1px rgba(177, 116, 63, 0.5);
	padding: 2rem;
	width: 100%;
	max-width: $container-max-w;

	@media (min-width: $md) {
		flex-direction: row;
		justify-content: space-between;
		padding: 1.5rem 2rem;
	}
	@media (min-width: $lg) {
		padding: 1.5rem 0 3rem;
	}

	&__social {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		list-style: none;
		margin: 1.25rem 0 0 0;
		padding: 0;
		transition: all 0.2s ease-in-out;

		@media (min-width: $md) {
			margin: 0;
		}

		svg {
			height: 24px;
			width: 24px;

			@media (min-width: $md) {
				height: 20px;
				width: 20px;
			}
		}
	}

	&__social--item {
		margin: 0 .5rem;
		padding: 0;
		cursor: pointer;

		@media (min-width: $md) {
			margin: 0 0 0 1rem;
		}
	}

	&__social--link {
		color: rgba(255, 255, 255, 0.5);
		font-size: 1.5rem;
		transition: color 0.3s ease;

		&:hover {
			color: rgba(255, 255, 255, 1);

			svg {
				transform: scale(1.1);
			}
		}
	}
}
</style>
