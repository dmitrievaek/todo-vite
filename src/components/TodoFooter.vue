<template>
	<div class="todo_footer">
		<div>{{tasks.length}} items</div>
		<ul class="todo_filters">
			<li class="todo_filters_item">
				<a href="#" @click="activeTab = 1" :class="{ selected: activeTab === 1 }">All</a>
			</li>
			<li class="todo_filters_item">
				<a href="#" @click="activeTab = 2" :class="{ selected: activeTab === 2 }">Active</a>
			</li>
			<li class="todo_filters_item">
				<a href="#" @click="activeTab = 3" :class="{ selected: activeTab === 3 }">Completed</a>
			</li>
		</ul>
		<my-button
			class="todo_clear"
			@click="clearCompleted"
		> Clear Completed
		</my-button>
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
		},
		activeTab: Number
	},
	methods:{
		clearCompleted(){
			
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
.todo_clear{
	padding: .625rem 1.5rem;
	background: #7ed6df;
	color: #fff;
	border: none;
	border-radius: .25rem;
	cursor: pointer;
	font-size:13px;
}
.todo_clear:hover{
	background: #22a6b3;
}
.todo_filters{
	display: flex;
	align-items: center;
	list-style: none;
}
.todo_filters_item{
	margin-right: 1rem;
}
.todo_filters_item a{
	position: relative;
	padding: .5rem 0;
	text-decoration: none;
	color: #000;
}
.todo_filters_item .selected{
	text-decoration:underline;
	text-decoration-color:red;
}
</style>