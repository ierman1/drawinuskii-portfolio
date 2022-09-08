<template>
	<div class="view contact">
		<h2>Contact me for comissions<br>or more info</h2>

		<form id="contact_form" @submit="submitContactForm">
			<input type="hidden" name="contact_number" v-model="contact_number">

			<div class="input-group">
				<label>Name</label>
				<input type="text" name="from_name" v-model="from_name" required>
			</div>

			<div class="input-group">
				<label>Email</label>
				<input type="email" name="from_email" v-model="from_email" required>
			</div>

			<div class="input-group">
				<label>Message</label>
				<textarea name="message" v-model="message" rows="8" required></textarea>
			</div>

			<div class="input-group">
				<VueRecaptcha
					:sitekey="'6Ld2Tt8hAAAAAHiFjbbQIt5iE8I0sPUJJWKF4uvh'"
					:load-recaptcha-script="true"
					@verify="handleSuccess"
					@error="handleError"
					@expired="handleError"
				></VueRecaptcha>
			</div>
			
			<div class="input-group">
				<button type="submit" :disabled="!captcha">Send</button>
			</div>
		</form>

	</div>
</template>

<style lang="scss">

.contact {
	margin-bottom: 5rem;

	h2 {
		text-align: center;
		font-size: 1.5rem;

		@media (min-width: 780px) {
			font-size: 2rem;
		}
	}

	form {
		.input-group {
			margin: auto;
			margin-top: 2rem;
			width: 80%;

			* {
				display: block;
				margin: auto;
				width: 100%;
				max-width: 450px;
			}

			label {
				font-weight: bold;
				margin-bottom: .7rem;
			}

			input, textarea {
				background-color: $light-color;
				border: none;
				box-shadow: none;
				font-family: 'Secular One';
				font-size: 16px;
				opacity: 70%;
				outline: none;
				padding: .6rem 1rem;
				transition: box-shadow .2s ease-in-out;

				&:focus {
					box-shadow: 0px 0px 10px 5px $primary-color;
				}
			}

			button {
				padding: 1rem 0;
				cursor: pointer;
				width: 100px;
			}
		}
	}
}

</style>

<script>

import emailjs from '@emailjs/browser'
import { VueRecaptcha } from 'vue-recaptcha';

export default {
	
	name: 'ContactView',
	components: {
		VueRecaptcha
	},
	data: () => {
		return {
			contact_number: 0,
			from_name: '',
			from_email: '',
			message: '',
			captcha: false
		}
	},
	mounted() {
		emailjs.init('aW9QIuYvgt8VGKc5g');
	},
	methods: {
		handleSuccess() {
			this.captcha = true;
		},
		handleError() {
			this.captcha = false;
		},
		submitContactForm(event) {
			event.preventDefault();

			// Validating
			if (!this.captcha || this.from_name.trim() == '' || this.from_email.trim() == '' || this.message.trim() == '')
				return;

			// EMAIL SENDING
			this.contact_number = Math.random() * 100000;
	
			emailjs.send('service_7k1q42x', 'template_y02a1h9', {
				contact_number: this.contact_number,
				from_name: this.from_name,
				from_email: this.from_email,
				message: this.message
			}).then(function() {
				console.log('SUCCESS!');
			}, function(error) {
				console.log('FAILED...', error);
			});
		}
	}

}
</script>
