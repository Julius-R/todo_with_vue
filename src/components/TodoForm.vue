import { v4 as uuidv4 } from 'uuid';
<template>
	<form class="todo_form" @submit.prevent="handleSubmit">
		<input type="text" v-model="description" />
		<button>Create Todo</button>
	</form>
</template>

<script>
import { v4 as uuidv4 } from "uuid";
export default {
	name: "TodoForm",
	data() {
		return {
			description: ""
		};
	},
	methods: {
		handleSubmit() {
			let todo = {
				id: uuidv4(),
				description: this.description
			};
			console.log(todo);
		}
	}
};
</script>
