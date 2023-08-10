<template>
<img alt="Vue logo" src="../assets/effo.png">

<!--slot></slot>
<slot name="named"></slot-->

<form class="form">
<input type="text" required v-model="tmpTask" />
<button @click.prevent="submit" >Add task</button>
</form>

<div v-for="task in tasks" class="tasks">
<span @click="finishTask(task)" >{{ task }}</span>
</div>
</template>

<script lang="ts">
export default {
	data() {
		return {
			tasks: [],
			tmpTask: ''
		}
	},
	methods: {
		submit() {
			if(this.tmpTask && !this.tasks.includes(this.tmpTask))
				this.tasks.push(this.tmpTask)
		},
		finishTask(task){
			this.tasks = this.tasks.filter((item) => {
				return task !== item
			})
		}
	}
}
</script>

<style>

form {
	max-width: 420px;
	margin: 30px auto;
	background: white;
	text-align: left;
	padding: 40px;
	border-radius: 10px;	
}
input{
	display: block;
	padding: 10px 6px;
	width: 100%;
	box-sizing: border-box;
	border: none;
	border-bottom: 1px solid #ddd;
	color: #555;
}

button{
	background-color: blue;
	border: 5px solid blue;
	color: white;
	padding: 15px 32px;
	text-align: center;
	text-decoration: none;
	display: inline-block;
	font-size: 16px;
}

button:hover{
	background-color: teal;
	color:black;
	border-radius: 8px;
}

.tasks{
	
	width: 100%;
	background-color: grey;
	color: black;

}
</style>