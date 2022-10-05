<script setup lang="ts">
	
	import { animate, spring, stagger  } from 'motion'

	let projects = ref([
		{
			title: "TictacDos",
			Thumb: "/projects/tictacdos.png",
			link: "https://tacticdos.web.app/",
			labels: ["Vuejs", "Tailwind", "WebRTC", "Drag&Drop"]
		},
		{
			title: "Landing Sanchte",
			Thumb: "/projects/sanchte.png",
			link: "https://sanchte.com/",
			labels: ["Javascript", "Vuejs", "Tailwind"]
		},
		{
			title: "Landing pinturas Shalom",
			Thumb: "/projects/shalom.png",
			link: "https://pinturasshalom.com/",
			labels: ["Javascript", "Vuejs", "Tailwind"]
		},
		{
			title: "landing Geotracking",
			Thumb: "/projects/geo.png",
			link: "https://geotracking.do/",
			labels: ["Vuejs", "Threejs", "Sass"]
		},
		{
			title: "landing Lugotech",
			Thumb: "/projects/lugotech.png",
			link: "https://www.lugotech.com.do/",
			labels: ["Javascript", "Vuejs", "Fullpagejs"]
		},
	])

	let rickCard = defineAsyncComponent(() => import('@/components/prototypes/rickCard.vue'))
	let eva = defineAsyncComponent(() => import('@/components/prototypes/eva.vue'))
	let krilinSticker = defineAsyncComponent(() => import('@/components/prototypes/krilinSticker.vue'))
	let gameboyCss = defineAsyncComponent(() => import('@/components/prototypes/gameboyCss.vue'))
	let dado = defineAsyncComponent(() => import('@/components/prototypes/dado.vue'))
	let figmaLogo = defineAsyncComponent(() => import('@/components/prototypes/figmaLogo.vue'))

	const expTitle = ref();
	let expInView = ref<boolean>(false);

	const Projectsection = ref();
	let projectsInView = ref<boolean>(false);

	onMounted(async () => {

		useIntersectionObserver(expTitle, ([{ isIntersecting }], observerElement) => {
			expInView.value = isIntersecting;
			
			if(isIntersecting){
				console.log("Intersectoooo")
				observerElement.disconnect();
			}
				
		})

		useIntersectionObserver(Projectsection, ([{ isIntersecting }], observerElement) => {
			projectsInView.value = isIntersecting;
			
			if(isIntersecting){
				console.log("Intersectoooo")
				observerElement.disconnect();
			}
				
		})


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

		}

</script>

<template>
	
		<div class="min-h-screen dark:bg-[#012A35] dark:text-white scroll-smooth">

			<!-- <h1 class="fixed top-0 left-0 origin-bottom-left rotate-90 text-7xl font-bold text-slate-700/10">|||||||||||||||||||||||||</h1> -->


			<div class="container mx-auto px-4 pt-20 pb-6">

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
									
							</div>
	
						</div>
	
						<div id="avatar" class="h-32 w-32 flex justify-center items-center border-4 dark:border-[#001E26] rounded-full dark:bg-[#012A35] absolute inset-y-0 -top-16 no-backface">
							<img src="@/assets/me.png" class="h-20" alt="">
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
							<img src="@/assets/me.png" class="h-24" alt="">
						</div>
		
					</div>
				</div>


				<div class="flex flex-wrap mt-14 mb-10 relative">

					<div class="absolute top-0 lg:-top-10 left-0 lg:left-10 select-none h-32 overflow-y-hidden">
						<h1 class="origin-bottom-left text-6xl lg:text-9xl font-bold text-slate-700/20">Some of my work</h1>
					</div>

					<div class="w-full lg:w-1/2 p-5 lg:border-l-4 border-slate-700 ">

						<h1 class="text-4xl lg:text-5xl font-bold relative">
							My work 
						</h1>

						<p class="relative text-2xl text-slate-500">
							These are some of the projects I`ve built for clients and at work.
						</p>

					</div>

				</div>

				<div ref="Projectsection"></div>

				<transition name="slide-fade">
					<div v-if="projectsInView" class="flex flex-wrap">
	
						<div class="w-full lg:w-4/12 lg:p-5 py-5 " v-for="(project, i) in projects" :key="i">
	
							<div class="relative">
								<div class="w-full dark:bg-[#001E26] rounded-xl relative overflow-hidden group shadow-lg shadow-[#294952]">

									<img :src="project.Thumb" class=" object-cover group-hover:scale-110 transition-all duration-300" alt="">

									<div class="flex justify-center items-center absolute inset-0 bg-white/40 backdrop-blur-lg dark:bg-[#001E26]/40 opacity-0 w-full h-full group-hover:opacity-100 transition-all duration-300">
										<a :href="project.link" target="_blank" class="p-3 bg-white/20  rounded-full border-2 text-4xl">
											<icon:heroicons-outline:external-link class=""/>
										</a>
									</div>

								</div>
		
								<div class="py-3 px-1">
		
									<h3 class="text-lg font-bold">
										{{ project.title }} <icon:heroicons-outline:external-link class="inline"/>
									</h3>
		
									<div class="flex flex-wrap gap-2 text-xs mt-3">
		
										<div v-for="label in project.labels" class="p-1 rounded-lg dark:bg-[#001E26]">
											{{ label }}
										</div>
		
									</div>
								</div>
							</div>
							
	
						</div>
					
					</div>
				</transition>



				<div ref="expTitle" class="flex flex-wrap mt-14 mb-10 relative">

					<div class="absolute top-0 lg:-top-10 left-0 lg:left-10 select-none h-32 overflow-y-hidden">
						<h1 class="origin-bottom-left text-6xl lg:text-9xl font-bold text-slate-700/20">
							Just for fun
						</h1>
					</div>

					<div class="w-full lg:w-1/2 p-5 lg:border-l-4 border-slate-700 ">

						<h1 class="text-4xl lg:text-5xl font-bold relative">
							Fun with code
						</h1>

						<p class="relative text-2xl text-slate-500">
							Things I do just for fun, most of what you see here is done with just css 😁.
						</p>

					</div>

				</div>

				<transition name="slide-fade">
					<div v-if="expInView" class="grid grid-cols-1 lg:grid-cols-3 rounded-3xl overflow-hidden">
	
						<div>
							<rick-card></rick-card>
						</div>
	
						<div>
							<krilin-sticker></krilin-sticker>
						</div>
	
						<div>
							<gameboy-css></gameboy-css>
						</div>
						<div>
							<eva></eva>
						</div>
						<div>
							<dado></dado>
						</div>
						<div>
							<figma-logo></figma-logo>
						</div>
	
					</div>
				</transition>



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

	/*
	Enter and leave animations can use different
	durations and timing functions.
	*/
	.slide-fade-enter-active {
	transition: all 0.5s ease-out;
	}

	.slide-fade-leave-active {
	transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
	}

	.slide-fade-enter-from,
	.slide-fade-leave-to {
	transform: translateY(120px);
	opacity: 0;
	}


</style>

<route lang="yaml">
name: home
</route>
