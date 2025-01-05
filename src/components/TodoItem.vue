<template>
	<div class="task">
		<label for="todo_pin" class="todo_app_pin" >
			<input class="todo_pin_item" type="checkbox" id="todo_pin" />
			<i class="todo_pin_icon"></i>
		</label>
		<label for="todo_checkbox" class="todo_app_checkbox" >
			<input class="todo_checkbox_item" type="checkbox" id="todo_checkbox" />
		</label>
		<div class="todo_item_name">{{ task.name }}</div>
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
	padding: 0.3rem 2rem 0.5rem 2rem;
}
.todo_app_pin{

}
.todo_pin_item{
	position: absolute;
    width: 15px;
    height: 15px;
    opacity:0;
    cursor: pointer;
}
.todo_pin_icon{
	opacity:0;
	width: 10px;
    height: 10px;
	display:inline-block;
	position:relative;
	margin-right:15px;
	cursor:pointer;
}
.todo_pin_icon:hover{
	opacity:1;
}
.todo_pin_icon:after {
    content: "\25B2";
	color:red;
	display: inline-block;
    font-size: 20px;
}
.todo_item_name{
	margin-right: 1rem;
    display: block;
    width: 100%;
    word-break: break-all;
    font-size: 1rem;
}
.todo_app_checkbox{
	margin-right: 1rem;
	margin-top: 0.3rem;
}
.todo_checkbox_item{
	width: 15px;
    height: 15px;
	cursor:pointer;
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