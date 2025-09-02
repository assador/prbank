<script setup lang="ts">
import { ref } from 'vue';

defineProps<{ list: string[] }>();

const filter = ref('');
</script>

<template>
	<h3>4. Простой фильтр</h3>
	<div>
		<input v-model="filter" type="text" />
	</div>
	<ul>
		<li v-for="item of list.filter(text => text.includes(filter))">
			{{ item }}
		</li>
	</ul>
</template>
