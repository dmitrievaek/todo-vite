<template>
	<div v-show="activeTab === 1">
		<div>
			<todo-item 
				v-for="task in tasks"
				:task="task"
				:key="task.id"
				@remove="$emit('remove', task)"
			/>	
		</div>
	</div>
	<div v-show="activeTab === 2">
		<div>
			<todo-item 
				v-for="task in tasks"
				:task="task"
				:key="task.id"
				@remove="$emit('remove', task)"
			/>	
		</div>
	</div>
	<div v-show="activeTab === 3">
		<div>
			<todo-item 
				v-for="task in tasks"
				:task="task"
				:key="task.id"
				@remove="$emit('remove', task)"
			/>	
		</div>
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
		},
		activeTab: Number
	}
}
</script>

<style scoped>
.todo_list{
	padding: 0.5rem 2rem;
}
</style>