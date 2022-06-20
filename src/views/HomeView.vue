<template>
	<h1 class="my-5">Formulario con Vue.js</h1>

	<form @submit.prevent="procesarFormulario">
		<Input :tarea="tarea" />
	</form>
	<hr />
	<p>
		{{ tarea }}
	</p>
</template>

<script>
	import Imput from "../components/Input.vue";

	export default {
		name: "HomeView",
		components: {
			Imput,
		},
		data() {
			return {
				tarea: {
					id: "",
					nombre: "",
					categorias: [],
					estado: "",
					numero: 0,
				},
			};
		},
		methods: {
			procesarFormulario() {
				console.log(this.tarea);
				if (this.tarea.nombre.trim() === "") {
					console.log("Esta vacío ");
					return;
				}
				console.log("no está vacío ");
				// para vaciar los campos
				this.tarea = {
					nombre: "",
					categorias: [],
					estado: "",
					numero: 0,
				};
			},
		},
	};
</script>
