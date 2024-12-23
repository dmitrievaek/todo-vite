<template>
	<div class="app">
		<todo-form
			@create="createTodo"
		/>
		<todo-list 
			:tasks="tasks"
			@remove="removeTodo"
		/>
		<todo-footer
			:tasks="tasks"
		/>
	</div>
</template>

<script>
import TodoForm from "./components/TodoForm.vue";
import TodoList from "./components/TodoList.vue";
import TodoFooter from "./components/TodoFooter.vue";

export default {
	components:{
		TodoForm, TodoList, TodoFooter
	},
	data(){
		return {
			tasks:[
				{id:1, name: 'Todo1'},
				{id:2, name: 'Todo2'},
				{id:3, name: 'Todo3'},
			],
		}
	},
	methods:{
		createTodo(task){
			this.tasks.push(task);
		},
		removeTodo(task){
			this.tasks = this.tasks.filter(p => p.id != task.id)
		}
	}
}
</script>

<style>
*{
	margin:0;
	padding:0;
	box-sizing:border-box;
	font-size:16px;
}
.app{
	width: 100%;
    max-width: 35rem;
    background: #fff;
    box-shadow: 0 0 20px 8px #223c5033;
    -webkit-box-shadow: 0px 0px 20px 8px rgba(34, 60, 80, .2);
    -moz-box-shadow: 0px 0px 20px 8px rgba(34, 60, 80, .2);
    border-radius: .25rem;
	padding: 0;
	margin: 20px auto;
}
</style>
