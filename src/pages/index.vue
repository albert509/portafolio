<script setup lang="ts">

	// import { animate, spring,  } from "motion"
	import { animate, spring, stagger, timeline  } from 'motion'
	
	useHead({
		title: '',
	});

	onMounted(async () => {

		nextTick(() => {

			window.addEventListener('mousemove', (ev: MouseEvent) => {

				let { clientX, clientY } = ev;

				document.documentElement.style.setProperty('--mouseX', `${clientX}`)
				document.documentElement.style.setProperty('--mouseY', `${clientY}`)

			})

		})

		animate('.desc', { y: [100, 0], opacity: [0,1] }, { easing: spring() });
		animate('.ani', { scale: [0,1], opacity: [0,1] }, { delay: stagger(0.3), easing: spring() });
		animate('.skill', { y: [100, 0], opacity: [0,1] }, { delay: stagger(0.1), easing: spring() })
		animate('#avatar', { y: [-100, 0], opacity: [0,1] }, { delay: 1, easing: spring() })

		

	})

</script>

<template>
	
		<div class="min-h-screen dark:bg-[#012A35] dark:text-white">

			<div id="navBar" class="h-20 w-full z-50">

				<div class="container mx-auto px-4">

					<div class="flex justify-center h-20 w-full relative z-50">

						<div id="avatar" class="h-32 w-32 flex justify-center items-center  dark:border-white rounded-full dark:bg-[#012A35] absolute inset-y-0 -bottom-16">
							<img src="@/assets/me.webp" class="h-24" alt="">
						</div>

					</div>

				</div>


			</div>

			<div class="container mx-auto px-4">

				<!-- <button>
					<icon:akar-icons:moon-fill class="h-8 w-8" v-if="true"/>
					<icon:akar-icons:sun-fill class="h-8 w-8" v-else/>
				</button> -->

				<div class="flex bg-white/60 px-5 lg:px-10 py-16 dark:bg-[#001E26] flex-wrap justify-center  dark:border-white shadow-lg rounded-3xl dark:text-white relative">
	
					<div class="lg:p-10 w-full lg:w-1/2">
	
						<div class="flex flex-col justify-center ">
	
							<!-- <div class="h-52 w-52 bg-gray-600 rounded-full"></div> -->
	
							<div class="desc lg:mt-0 mt-5">
								<h1 class="text-2xl lg:text-4xl font-bold text-center lg:text-left">
									Hi, Im Luis Alberto
								</h1>
	
								<h2 class="text-xl lg:text-2xl font-bold text-center lg:text-left mb-5 dark:text-slate-200">
									FullStack web developer
								</h2>
		
								<h2 class="text-lg lg:text-xl text-center lg:text-justify dark:text-slate-300">
									I am a full stack web developer based in Dominican Republic with experience developing applications in Asp.net Core and vuejs.<span class="font-bold typing-animation">|</span>
								</h2>

								<h3 class="text-2xl mt-10 lg:mt-5 text-center lg:text-left">
									Contact
								</h3>
								<h4 class="underline underline-offset-4 text-center lg:text-left">
									albertalmonte89@gmail.com
								</h4>
							</div>



							<div class="w-full flex flex-wrap gap-5  py-5 justify-center lg:justify-start">

								<div class=" ">

									<div class="ani border-2 border-black dark:border-white hover:bg-white hover:text-black select-none cursor-pointer p-3 rounded-xl text-center">
										<icon:akar-icons:linkedin-box-fill class="inline"/>
									</div>

								</div>

								<div class=" ">

									<div class="ani border-2 border-black dark:border-white hover:bg-white hover:text-black select-none cursor-pointer p-3 rounded-xl text-center">
										<icon:akar-icons:codepen-fill class="inline"/>
									</div>
								</div>

								<div class=" ">
									<div class="ani border-2 border-black dark:border-white hover:bg-white hover:text-black select-none cursor-pointer p-3 rounded-xl text-center">
										<icon:akar-icons:twitter-fill class="inline"/>
									</div>

								</div>


								<div class=" ">

									<div class="ani border-2 border-black dark:border-white hover:bg-white hover:text-black select-none cursor-pointer p-3 rounded-xl text-center">
										<icon:akar-icons:github-fill class="inline"/>
									</div>
								</div>

							</div>
						</div>
					</div>

					<div class="lg:p-10 w-full lg:w-1/2">

						<div class="" v-for="a in 1">

							<h1 class="text-4xl mb-10 mt-10 lg:mt-0 font-bold">
								My skills cloud
							</h1>

							<div class="flex flex-wrap text-black justify-center lg:justify-start">

								<div class="skill rounded-lg bg-white  shadow-md mb-5 p-3 m-1">
									<icon:teenyicons:javascript-solid class="inline"/> Javascript
								</div>
								<div class="skill rounded-lg bg-white  shadow-md mb-5 p-3 m-1">
									<icon:teenyicons:html5-solid class="inline"/> HTML
								</div>
								<div class="skill rounded-lg bg-white  shadow-md mb-5 p-3 m-1">
									<icon:teenyicons:css3-solid class="inline"/> CSS
								</div>

								<div class="skill rounded-lg bg-white  shadow-md mb-5 p-3 m-1">
									<icon:teenyicons:vue-solid class="inline"/> Vuejs
								</div>
								<div class="skill rounded-lg bg-white  shadow-md mb-5 p-3 m-1">
									<icon:teenyicons:nuxtjs-solid class="inline"/> Nuxtjs
								</div>
								<div class="skill rounded-lg bg-white  shadow-md mb-5 p-3 m-1">
									<icon:mdi:vuetify class="inline"/> Vuetify
								</div>
								<div class="skill rounded-lg bg-white  shadow-md mb-5 p-3 m-1">
									<icon:teenyicons:tailwind-solid class="inline"/> TailwindCss
								</div>


								<div class="skill rounded-lg bg-white  shadow-md mb-5 p-3 m-1">
									<icon:teenyicons:firebase-solid class="inline"/> Firebase
								</div>



								<div class="skill rounded-lg bg-white  shadow-md mb-5 p-3 m-1">
									<icon:teenyicons:nodejs-solid class="inline"/> NodeJs
								</div>
								<div class="skill rounded-lg bg-white  shadow-md mb-5 p-3 m-1">
									<icon:teenyicons:mongodb-solid class="inline"/> MongoDb
								</div>
								

								<div class="skill rounded-lg bg-white  shadow-md mb-5 p-3 m-1">
									<icon:teenyicons:typescript-solid class="inline"/> MongoDb
								</div>

								<div class="skill rounded-lg bg-white  shadow-md mb-5 p-3 m-1">
									<icon:teenyicons:c-sharp-solid class="inline"/> C#
								</div>

								<div class="skill rounded-lg bg-white  shadow-md mb-5 p-3 m-1">
									<icon:bi:filetype-sql class="inline"/> SQL databases
								</div>
								
							</div>

						</div>

					</div>

					<!-- <div id="avatar" class="h-32 w-32 flex justify-center items-center  dark:border-white rounded-full dark:bg-[#012A35] absolute inset-y-0 -top-16">
						<img src="@/assets/me.webp" class="h-24" alt="">
					</div> -->

					<!-- <div class="mousePosition"></div> -->
	
				</div>

				<!-- <div class="flex flex-wrap">

					<div class="p-10 w-full lg:w-1/2 mt-5 ">

						<h1 class="text-6xl  font-bold">
							👨🏾‍💻 My work
						</h1>

					</div>


				</div> -->

				<!-- <div class="flex">

					<div class="w-1/2">
						<iframe height="688.6666870117188" style="width: 100%;" scrolling="no" title="Interactive GameBoy ( HTML &amp; CSS )" src="https://codepen.io/albert509/embed/dydPzZa?default-tab=result&theme-id=dark" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
						See the Pen <a href="https://codepen.io/albert509/pen/dydPzZa">
						Interactive GameBoy ( HTML &amp; CSS )</a> by Luis Alberto (<a href="https://codepen.io/albert509">@albert509</a>)
						on <a href="https://codepen.io">CodePen</a>.
						</iframe>
					</div>

				</div> -->

			</div>




		</div>


</template>

<style lang="scss">

	.mousePosition{

		position: fixed;

		transition: all;
		transition-duration: 0.1s;
		transition-timing-function: linear;

		height: 50px;
		width: 50px;
		border-radius: 50%;

		transform: scale(1);

		backdrop-filter: invert(70%);

		top: calc((var(--mouseY) * 1px) - 25px);
		left: calc((var(--mouseX) * 1px) - 25px);

	}

	@keyframes typing{
		0%{
			opacity: 0;
		}
		50%{
			opacity: 1;
		}
		100%{
			opacity: 0;
		}
	}

	.typing-animation{
		animation: typing;
		animation-duration: 1s;
		animation-iteration-count: infinite;
		animation-timing-function: linear;
	}


</style>

<route lang="yaml">
name: home
</route>
