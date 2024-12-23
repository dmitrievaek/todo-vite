<template>
	<div v-if="tasks.length > 0">
		<todo-item 
			v-for="task in tasks"
			:task="task"
			:key="task.id"
			@remove="$emit('remove', task)"
		/>	
	</div>
	<div class="todo_list" v-else>
		Список пуст!
	</div>
	<br/>
</template>

<script>
import TodoItem from "/src/components/TodoItem.vue";
export default {
	components:{TodoItem},
	props: {
		tasks:{
			type: Array,
			required: true,
		}
	}
}
</script>

<style scoped>
.todo_list{
	padding: 0.5rem 2rem;
}
</style>