<script setup>
import HouseIcon from '../components/HouseIcon.vue'
import CarIcon from '../components/CarIcon.vue'
</script>

<template>
	<section>
		<div class="container">
			<div class="img-container">
				<div class="car-background">
					<div class="car-tire"></div>
					<div class="car-tire"></div>

				</div>
				<div class="trace"></div>
				<div class="trace-bg-large"></div>
				<div class="trace-bg-little"></div>
			</div>

			<div class="title-container title-container1">
				<p class="marquee">
					<span>Body Salon Dis Brakes -&nbsp;</span>
				</p>
				<p class="marquee marquee2">
					<span>Body Salon Dis Brakes -&nbsp;</span>
				</p>
			</div>
			<div class="title-container title-container2">

				<p class="marquee">
					<span>Cabrio Glass Windshield -&nbsp;</span>
				</p>
				<p class="marquee marquee2">
					<span>Cabrio Glass Windshield -&nbsp;</span>
				</p>
			</div>

			<div class="description-container">
				<h1>
					Kulasta suurim iluravikeskus tehnikale
				</h1>
				<p>
					oleme suuremate voimalustega ja teenuste loetu detaling keskus, us saab Teie tehnikale saada professionaalne
					teenindus. Teenused pakkume nii autodele, moto- voi veetehnikale, kuid ka lennukitele ja kodu asjadele.
				</p>

				<div class="navigation-container">
					<div class="item">
						<div class="icon-container">
							<CarIcon />
						</div>
						<p>
							Auto
						</p>
					</div>

					<div class="item">
						<div class="icon-container">
							<HouseIcon />
						</div>
						<p>
							House
						</p>
					</div>

				</div>
			</div>
		</div>
	</section>
</template>

<style lang="scss" scoped>
$primary: #d84c4d;

section {
	max-width: 1300px;
	overflow: hidden;
	margin: 0 auto;
	height: inherit;
	transition: 2s ease;

	@keyframes opening {
		0% {
			width: 2px;
			overflow: hidden;
		}

		to {
			width: 1300px;
			overflow: visible;
		}
	}
}

.container {
	border: 2px solid rebeccapurple; //$primary; //rebeccapurple
	border-radius: 25px;
	position: relative;
	background-color: #fff;
}

.title-container {
	height: 100px;
	position: absolute;
	overflow: hidden;

	&.title-container1 {
		width: 60%;
		right: 0;
		top: 32%;
		transform: translateY(-40%);
		z-index: 0;
	}

	&.title-container2 {
		@media screen and (min-width: 960px) {
			right: -31%;
		}

		width: 85%;
		top: 45%;
		transform: translateY(-50%);
		z-index: 0;
	}

	.marquee {
		color: #e9e9e9;
		font-size: 5rem;
		font-weight: 500;
		text-transform: uppercase;
		margin: 0 auto;
		white-space: nowrap;
		overflow: hidden;
		position: absolute;
	}

	.marquee span {
		display: inline-block;
		padding-left: 100%;
		animation: marquee 7s 2.5s linear infinite forwards;
	}

	.marquee2 span {
		animation-delay: 6s; //(half of 7 + 4s delay)
	}

	@keyframes marquee {
		0% {
			transform: translate(0, 0);
		}

		100% {
			transform: translate(-100%, 0);
		}
	}
}

.img-container {
	display: block;
	width: 100%;
	padding: 90px;
	position: relative;
	animation-name: translateBgX;
	animation-duration: 2s;
	transform: translateX(-300px);
	z-index: 1;

	.car-background {
		width: 660px;
		height: 250px;

		// width: 800px;
		// height: 300px;
		@media screen and (min-width: 960px) {
			width: 1000px;
			height: 400px;
		}

		position: relative;
		z-index: 1;
		background-image: url('../assets/img/porshe_model.png');
		background-position: center;
		background-size: cover;
		animation-name: translateBgX;
		animation-duration: 2s;
	}

	.car-tire {
		// width: 146px;
		// height: 121px;
		background-position: center;
		background-size: contain;
		background-repeat: no-repeat;
		animation-name: rotate;
		animation-duration: 2s;

		&:first-child {
			background-image: url('../assets/img/porshe_tire3.png');
			position: absolute;
			// bottom: 3px;
			// left: 126px;
			width: 26%;
			height: 40%;
			left: 12%;
			bottom: 2%;
		}

		&:nth-child(2) {
			width: 22%;
			height: 37%;
			right: 12%;
			bottom: 3%;
			background-image: url('../assets/img/porshe_tire3.png');
			position: absolute;
			// bottom: 0px;
			// right: 112px;
		}
	}

	.trace {
		background-color: #d84c4d;
		border-radius: 80px;
		transform: rotate(45deg);
		position: absolute;
		clip-path: polygon(0% -8%, 95% -34%, 49% 89%, 0% 100%);

		animation-name: growUp;
		animation-delay: 2s;
		animation-duration: 1s;
		animation-fill-mode: forwards;
	}

	// }
}

.trace-bg-large {
	width: 510px;
	height: 130px;
	background-color: #d84c4d;
	border-radius: 80px;
	transform: rotate(45deg);
	position: absolute;
	top: 33%;
	z-index: -1;
	opacity: 0;

	animation-name: growUp2;
	animation-delay: 3s;
	animation-duration: 1.5s;
	animation-fill-mode: forwards;
}

.trace-bg-little {
	width: 200px;
	height: 130px;
	background-color: #d84c4d;
	border-radius: 80px;
	transform: rotate(45deg);
	position: absolute;
	right: 15%;
	top: 9%;
	z-index: -1;
	opacity: 0;

	animation-name: growUp3;
	animation-delay: 3s;
	animation-duration: 1.5s;
	animation-fill-mode: forwards;

}

.description-container {
	max-width: 320px;
	margin-left: auto;
	margin-right: auto;
	color: #000;

	@media screen and (min-width: 960px) {
		display: flex;
		justify-content: space-around;
		align-items: center;
		max-width: 100%;
		margin-left: auto;
		margin-right: auto;
		padding-left: 100px;
		padding-right: 100px;
		gap: 30px;
	}

	h1 {
		max-width: 333px;
		font-size: 2rem;
		font-weight: 500;
		text-transform: uppercase;
		opacity: 0;
		animation-name: fade;
		animation-duration: 2s;
		animation-delay: 4s;
		animation-fill-mode: forwards;
	}

	p {
		max-width: 300px;
		font-size: .9rem;
		font-weight: 400;
		opacity: 0;
		animation-name: fade;
		animation-duration: 2s;
		animation-delay: 4.5s;
		animation-fill-mode: forwards;
	}

	.navigation-container {
		display: flex;
		justify-content: space-between;
		align-items: center;
		min-width: 200px;
		max-width: 200px;
		opacity: 0;
		animation-name: fade;
		animation-duration: 2s;
		animation-delay: 5s;
		animation-fill-mode: forwards;

		.item {
			display: flex;
			flex-direction: column;
			text-align: center;

			&:first-child {
				position: relative;

				&::after {
					content: "";
					width: 100px;
					height: 1px;
					background-color: $primary;
					position: absolute;
					top: 24px;
					left: 50px;
				}

				.icon-container {
					background-color: $primary;
					cursor: pointer;
					transition: .6s ease;

					&:hover {
						background-color: #fff;
						border: 1px solid $primary;

						svg {
							fill: $primary;
						}
					}
				}

				svg {
					height: 20px;
					fill: #fff;
					transition: .6s ease;
				}
			}

			&:last-child {
				.icon-container {
					border: 1px solid $primary;
					cursor: pointer;
					transition: .6s ease;

					&:hover {
						background-color: $primary;
						border: 1px solid #fff;

						svg {
							fill: #fff;
						}
					}
				}

				svg {
					// width: 50px;
					height: 25px;
					fill: $primary;
				}
			}
		}

		.icon-container {
			display: flex;
			justify-content: center;
			align-items: center;
			// padding: 20px;
			border-radius: 50%;
			min-width: 50px;
			min-height: 50px;

		}

		p {
			margin-top: 5px;
			font-size: .7rem;
			font-weight: 400;
			text-transform: uppercase;
		}
	}
}

// Car animation
@keyframes translateBgX {
	0% {
		transform: translateX(-1000px);
		filter: blur(5px);
	}

	100% {
		transform: translateX(-150px);
		filter: blur(0px);
	}
}

// trace animation
@keyframes growUp {
	0% {
		width: 0px;
		height: 0px;
		bottom: 25%;
		right: 40%;
		opacity: 0;
		mix-blend-mode: overlay;
	}

	100% {
		width: 354px;
		height: 130px;
		bottom: 19%;
		right: 34%;
		opacity: .7;
		mix-blend-mode: overlay;
		z-index: 1;
	}
}

// trace big animation
@keyframes growUp2 {
	0% {
		width: 0;
		right: 35%;
		opacity: 0;
	}

	100% {
		width: 510px;
		right: 15%;
		opacity: 1;
	}
}

// trace little animation
@keyframes growUp3 {
	0% {
		width: 0;
		top: 9%;
		opacity: 0;
	}

	100% {
		width: 200px;
		top: 9%;
		opacity: 1;
	}
}

// Tires animation
@keyframes rotate {
	from {
		transform: rotate(-360deg);
		filter: blur(2px);
	}

	to {
		transform: rotate(0deg);
		filter: blur(0px);
	}
}

@keyframes fade {
	from {
		opacity: 0;
	}

	to {
		opacity: 1;
	}
}</style>
