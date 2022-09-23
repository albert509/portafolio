<script setup lang="ts">


	let data = ref<any[]>([])

	let loadData = async () => {

		let response = await fetch('https://jsonplaceholder.typicode.com/todos')

		data.value = (await response.json()).slice(0, 5)

	}

	onMounted(async () => {

		await loadData();

	})


</script>

<template>

	<form action="">
		<input type="text" required>
		<input type="email">
		<input type="submit">
	</form>


</template>

<style>



.modal{

	position: fixed;
	top: 0; left: 0; right: 0; bottom: 0;
	background: rgba(0,0,0,0.5);

	display: flex;
	justify-content: center;
	align-items: center;

}

.ventana{
	height: 300px;
	width: 600px;
	padding: 10px;

	background-color: white;
	border-radius: 10px;
}

.hidden{
	display: none;
}

.container{
	padding: 0 10px;
	margin: 0 auto;
}

.row{

	display: flex;
	flex-wrap: wrap;
	

}

.col{
	width: 100%;
	padding: 10px;
}

.squeare{
	height: 100px;
	width: 100%;
	background: teal;
}

	
@media (min-width: 576px) {

	.col{
		width: 100%;
		padding: 10px;
	}

}


@media (min-width: 768px) { 

	.col{
		width: 50%;
		padding: 10px;
	}

}


@media (min-width: 992px) { 

	.col{
		width: 25%;
		padding: 10px;
	}

 }



</style>

<route lang="yaml">
name: other-page
</route>
