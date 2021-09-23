<template>
	<section class="todo">
		<p v-if="todos.length <= 0">No todos!</p>
		<ul class="todo_list">
			<todo-item
				v-for="todo in todos"
				:key="todo.id"
				:todo="todo"
				@delete:todo="deleteTodo"
			/>
		</ul>
	</section>
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
	name: "Todo",
	components: {
		TodoItem
	},
	data() {
		return {
			todos: [
				{ id: 0, description: "Learn Vue.js" },
				{ id: 1, description: "Learn React.js" }
			]
		};
	},
	methods: {
		deleteTodo(todo) {
			this.todos = this.todos.filter((t) => t.id !== todo.id);
		}
	}
};
</script>
