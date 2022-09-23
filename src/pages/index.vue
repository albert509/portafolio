<script setup lang="ts">

	// import { animate, spring,  } from "motion"
	import { animate, spring, stagger, timeline  } from 'motion'
	
	useHead({
		title: '',
	});

	onMounted(async () => {

		nextTick(() => {

			// let touchstartX = 0
			// let touchendX = 0
				
			// function checkDirection() {
			// 	// if (touchendX < touchstartX) voltea()
			// 	if ((touchendX < touchstartX) && Math.abs(touchendX - touchstartX) > 100) voltea('left')
			// 	if ((touchendX > touchstartX) && Math.abs(touchendX - touchstartX) > 100) voltea('right')
			// }

			// 	document.addEventListener('touchstart', e => {
			// 		touchstartX = e.changedTouches[0].screenX
			// 		console.log(touchstartX)
			// 	})

			// 	document.addEventListener('touchend', e => {
			// 	touchendX = e.changedTouches[0].screenX
			// 	console.log(touchendX)
			// 	checkDirection()
			// })

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

		animate('#cartaBack', { rotateY: 180 }, { duration: 0 })
		animate('#avatar2', { rotateY: 180 }, { duration: 0 })



		

	})

		let voltea = ( direccion: string ) => {

			if(direccion === 'right'){

				animate('#carta', { rotateY: 0 }, { easing: spring() })
				animate('#avatar', { rotateY: 0 }, { easing: spring() })

				animate('#cartaBack', { rotateY: 180 }, { easing: spring() })
				animate('#avatar2', { rotateY: 180 }, { easing: spring() })

			}else{

				animate('#carta', { rotateY: -180 }, { easing: spring() })
				animate('#avatar', { rotateY: -180 }, { easing: spring() })

				animate('#cartaBack', { rotateY: 0 }, { easing: spring() })
				animate('#avatar2', { rotateY: 0 }, { easing: spring() })

			}

			// window.scrollTo(0, 0);

			// animate('#cartaBack', { transform: ['rotateX(0deg)'] }, { easing: spring() })
			// animate('#avatar2', { transform: ['rotateX(0deg)'] }, { easing: spring() })
		}

</script>

<template>
	
		<div class="min-h-screen dark:bg-[#012A35] dark:text-white scroll-smooth">


			<div class="container mx-auto px-4 pt-14 pb-6">

				<div class="grid grid-cols-1 grid-rows-1 perspect">

					<div id="carta" class="col-start-1 row-start-1 flex bg-white/60 px-5 lg:px-5 pt-16 dark:bg-[#001E26] flex-wrap justify-center  dark:border-white shadow-lg rounded-3xl dark:text-white relative no-backface">
		
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

									<a href="mailto:albertalmonte89@gmail.com">
										<h4 class="underline underline-offset-4 text-center lg:text-left hover:font-bold">
											albertalmonte89@gmail.com
										</h4>
									</a>
								</div>
	
	
	
								<div class="w-full flex flex-wrap gap-5  py-5 justify-center lg:justify-start">
	
									<div class=" ">
	
										<a href="https://www.linkedin.com/in/luis-almonte-25b4a6232" target="_blank" class="ani block border-2 border-black dark:border-white hover:bg-white hover:text-black select-none cursor-pointer p-3 rounded-xl text-center">
											<icon:akar-icons:linkedin-box-fill class="inline"/>
										</a>
	
									</div>
	
									<div class=" ">
	
										<a href="https://codepen.io/albert509" target="_blank" class="ani block border-2 border-black dark:border-white hover:bg-white hover:text-black select-none cursor-pointer p-3 rounded-xl text-center">
											<icon:akar-icons:codepen-fill class="inline"/>
										</a>
									</div>
	
									<div class=" ">
										<a href="https://twitter.com/albert_almonte" target="_blank" class="ani block border-2 border-black dark:border-white hover:bg-white hover:text-black select-none cursor-pointer p-3 rounded-xl text-center">
											<icon:akar-icons:twitter-fill class="inline"/>
										</a>
	
									</div>
	
	
									<div class=" ">
	
										<a href="https://github.com/albert509" target="_blank" class="ani block border-2 border-black dark:border-white hover:bg-white hover:text-black select-none cursor-pointer p-3 rounded-xl text-center">
											<icon:akar-icons:github-fill class="inline"/>
										</a>
									</div>
	
								</div>
							</div>
						</div>
	
						<div class="lg:p-10 w-full lg:w-1/2">
	
							<div class="">
	
								<h1 class="text-3xl lg:text-4xl text-center lg:text-left mb-5 mt-10 lg:mt-0 font-bold">
									My skills cloud
								</h1>
	
								<div class="flex flex-wrap text-black justify-center lg:justify-start">
	
									<div class="skill rounded-lg shadow-md mb-5 m-1">
										<img src="@/assets/skillIcons/JavaScript.svg" class="h-14 lg:h-20" alt="">
									</div>

									<div class="skill rounded-lg shadow-md mb-5 m-1">
										<img src="@/assets/skillIcons/HTML.svg" class="h-14 lg:h-20" alt="">
									</div>

									<div class="skill rounded-lg shadow-md mb-5 m-1">
										<img src="@/assets/skillIcons/CSS.svg" class="h-14 lg:h-20" alt="">
									</div>

									<div class="skill rounded-lg shadow-md mb-5 m-1">
										<img src="@/assets/skillIcons/VueJS-Dark.svg" class="h-14 lg:h-20" alt="">
									</div>

									<div class="skill rounded-lg shadow-md mb-5 m-1">
										<img src="@/assets/skillIcons/NuxtJS-Dark.svg" class="h-14 lg:h-20" alt="">
									</div>

									<div class="skill rounded-lg shadow-md mb-5 m-1">
										<img src="@/assets/skillIcons/TailwindCSS-Dark.svg" class="h-14 lg:h-20" alt="">
									</div>

									<div class="skill rounded-lg shadow-md mb-5 m-1">
										<img src="@/assets/skillIcons/Firebase-Dark.svg" class="h-14 lg:h-20" alt="">
									</div>

									<div class="skill rounded-lg shadow-md mb-5 m-1">
										<img src="@/assets/skillIcons/NodeJS-Dark.svg" class="h-14 lg:h-20" alt="">
									</div>

									<div class="skill rounded-lg shadow-md mb-5 m-1">
										<img src="@/assets/skillIcons/MongoDB.svg" class="h-14 lg:h-20" alt="">
									</div>

									<div class="skill rounded-lg shadow-md mb-5 m-1">
										<img src="@/assets/skillIcons/TypeScript.svg" class="h-14 lg:h-20" alt="">
									</div>

									<div class="skill rounded-lg shadow-md mb-5 m-1">
										<img src="@/assets/skillIcons/CS.svg" class="h-14 lg:h-20" alt="">
									</div>

									<div class="skill rounded-lg shadow-md mb-5 m-1">
										<img src="@/assets/skillIcons/DotNet.svg" class="h-14 lg:h-20" alt="">
									</div>

									<div class="skill rounded-lg shadow-md mb-5 m-1">
										<img src="@/assets/skillIcons/Sass.svg" class="h-14 lg:h-20" alt="">
									</div>
									
								</div>
								
								<!-- <div class="flex flex-wrap text-black justify-center lg:justify-start">
	
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
									
								</div> -->

	
							</div>
	
						</div>
	
						<div id="avatar" class="h-32 w-32 flex justify-center items-center  dark:border-white rounded-full dark:bg-[#012A35] absolute inset-y-0 -top-16 no-backface">
							<img src="@/assets/me.webp" class="h-24" alt="">
						</div>
	
						<!-- <div class="mousePosition"></div> -->
		
					</div>

					<div id="cartaBack" class="col-start-1 row-start-1 flex bg-white/60 px-5 lg:px-10 py-16 dark:bg-[#001E26] flex-wrap justify-center  dark:border-white shadow-lg rounded-3xl dark:text-white relative no-backface rotate-To-back">
		
						<div class="lg:p-10 w-full lg:w-1/2">
		
							<div class="flex flex-col justify-center ">
		
								<h1 class="text-2xl lg:text-4xl font-bold text-center lg:text-left">
									My web dev journey
								</h1>
							
							</div>
						</div>
	
						<div id="avatar2" class="h-32 w-32 flex justify-center items-center  dark:border-white rounded-full dark:bg-[#012A35] absolute inset-y-0 -top-16 no-backface rotate-To-back">
							<img src="@/assets/me.webp" class="h-24" alt="">
						</div>
		
					</div>
				</div>


				<!-- <div class="flex flex-wrap mt-5">

					<div class="w-full p-5">

						<h1 class="text-4xl lg:text-5xl text-center font-bold">
							My work 👨🏾‍💻 
						</h1>

					</div>

				</div> -->

				<!-- <div class="flex flex-wrap">

					<div class="w-full lg:w-1/2 p-5" v-for="n in 5">

						<div class="w-full h-80 dark:bg-[#001E26] rounded-3xl relative">

							<div class="">

							</div>

						</div>

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

	.perspect{
		perspective: 1200px;
	}

	.no-backface{
		backface-visibility: hidden;
		// transform: rotateX(30deg);
	}


</style>

<route lang="yaml">
name: home
</route>
