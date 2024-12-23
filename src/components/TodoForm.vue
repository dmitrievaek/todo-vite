<template>
	<form @submit.prevent>
		<my-input
			v-model="task.name"
			type="text"
			placeholder="New Todo"
		/>
		<my-button
			class="todo_btn"
			@click="createTodo"
		> Add
		</my-button>
	</form>
</template>

<script>

export default {

	data(){
		return {
			task:{
				name:''
			}
		}
	},
	methods:{
		createTodo(){
			this.task.id = Date.now();
			this.$emit('create', this.task)
			this.task = {
				name:''
			}
		}
	}
}
</script>

<style scoped>
form{
	padding: 1.5rem 2rem 1rem 2rem;
}
.todo_btn{
	padding: 0.7rem 1.5rem;
    background: red;
    color: #fff;
    border: none;
    border-radius: .25rem;
    cursor: pointer;
    transition: background .2s ease-out;
}
</style>