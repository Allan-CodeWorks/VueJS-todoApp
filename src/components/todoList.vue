<script>
import TodoItem from './todoItem.vue'

export default {

	props: {
		itemList: { list: Array }
	},
	data() {
		return {
			done: false,
		};
	},
	methods: {

		handleRemove(itemText) {
			this.itemList.list = this.itemList.list.filter(i => i != itemText)
		}
	},
	components: { TodoItem }
}
</script>

<template>
	<ul>
		<TodoItem @remove="handleRemove" v-for="(item) in this.itemList.list" :text="item">
		</TodoItem>
	</ul>
</template>

