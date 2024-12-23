<template>
	<div class="todo_footer">
		<div>{{tasks.length}} items</div>
	</div>
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
.todo_footer{
	display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
    padding: 1rem 2rem;
    border-bottom-left-radius: .25rem;
    border-bottom-right-radius: .25rem;
    background-color: #c7ecee;
}
</style>