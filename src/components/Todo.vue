<template>
	<section class="todo">
		<todo-form />
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
import TodoForm from "./TodoForm.vue";
export default {
	name: "Todo",
	components: {
		TodoItem,
		TodoForm
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
		deleteTodo(id) {
			this.todos = this.todos.filter((todo) => todo.id !== id);
		},
		addTodo(todo) {
			this.todos = [todo, ...this.todos];
		}
	}
};
</script>
