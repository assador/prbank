<script setup lang="ts">
import { ref } from 'vue';

const value = ref(0);
</script>

<template>
	<h3>5. Обработка событий</h3>
	<div>
		<button @click="++value">Увеличить</button>&#160;
		<span>Значение: {{ value }}</span>
	</div>
</template>
