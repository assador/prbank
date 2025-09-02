<script setup lang="ts">
import { ref } from 'vue';
const color = ref({
	redColor: {
		class: 'red',
		text: 'красный',
	},
	greenColor: {
		class: 'green',
		text: 'зелёный',
	},
} as Record<string, {class: string, text: string}>);
const current = ref('redColor');
</script>

<template>
	<h3>2. Динамическое изменение стиля</h3>
	<p :class="color[current].class">
		<button @click="current = (current === 'redColor' ? 'greenColor' : 'redColor')">
			Поменять цвет
		</button>&#160;
		<span>Цветной текст: {{ color[current].text }}</span>
	</p>
</template>

<style scoped>
.red {
	color: rgb(255, 0, 0);
}
.green {
	color: rgb(0, 128, 0);
}
</style>
