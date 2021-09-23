<template>
	<li class="list_item">
		<span>{{ todo.description }}</span>
		<button @click="$emit('delete:todo', todo.id)">Delete</button>
	</li>
</template>

<script>
export default {
	name: "TodoItem",
	props: ["todo"]
};
</script>
