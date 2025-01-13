<template>
	<input
		class="todo_input"
		type="text"
		:value="modelValue"
		@input="updateInput"
	>
</template>

<script>
export default {
	name: 'my-input',
	props:{
		modelValue:[String, Number]
	},
	methods:{
		updateInput(event){
			this.$emit('update:modelValue', event.target.value)
		}
	}
}
</script>

<style scoped>
.todo_input{
	margin-right: 1rem;
	padding: .625rem 1rem;
	width: 81%;
	border: 1px solid #808080;
	border-radius: .25rem;
}
.todo_input:focus{
	outline: 1px solid red;
}
</style>