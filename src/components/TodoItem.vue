<template>
	<div class="task">
		<div>{{ task.name }}</div>
		<my-button 
			class="del_btn"
			@click="$emit('remove', post)"
		>
			
		</my-button>
	</div>
</template>

<script>

export default {

	props: {
		task:{
			type: Array,
			required: true,
		}
	}
}
</script>

<style scoped>
.task {;
	display:flex;
	align-items:center;
	justify-content:space-between;
	padding: 0.3rem 2rem 0.5rem 2rem;
}
.del_btn{
	position: relative;
    width: 1.5rem;
    height: 1.5rem;
    border: none;
    cursor: pointer;
    background: transparent;
}
.del_btn:before, .del_btn:after {
    content: "";
    position: absolute;
    top: 50%;
    left: 50%;
    width: 1rem;
    height: 2px;
    background-color: red;
}
.del_btn:after{
	transform: translate(-50%, -50%) rotate(-45deg);
}
.del_btn:before{
	transform: translate(-50%, -50%) rotate(45deg);
}
</style>