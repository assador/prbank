<script setup lang="ts">
import { ref } from 'vue';
import Filter from './Filter.vue';

const list = ref([] as string[]);
const newItem = ref('');

const addNew = (text: string): void => {
	list.value.push(text);
}
</script>

<template>
	<h3>3. Список с добавлением элементов</h3>
	<div>
		<input v-model="newItem" type="text" />&#160;
		<button @click="addNew(newItem)">
			Добавить
		</button>
	</div>
	<ul>
		<li v-for="item of list">
			{{ item }}
		</li>
	</ul>
	<Filter :list="list" />
</template>
