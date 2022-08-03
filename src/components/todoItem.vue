<script>
export default {
	props: {
		text: '',
		index: 0
	},
	data() {
		return {
			isDone: false
		}
	},

}
</script>

<template>
	<li :class="{ done: isDone }"><input type="checkbox" v-model="isDone"> {{ text }}
		<button @click="$emit('remove', text)">Delete</button>
	</li>
</template>

<style scoped>
li.done {
	text-decoration: line-through;
}
</style>