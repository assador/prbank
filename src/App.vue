<script setup lang="ts">
import { ref } from 'vue';
import Name from './components/Name.vue';
import Style from './components/Style.vue';
import List from './components/List.vue';
import Counter from './components/Counter.vue';
import Users from './components/Users.vue';
import Type from './components/Type.vue';
import Decorator from './components/Decorator.vue';
import Merge from './components/Merge.vue';
import Array from './components/Array.vue';

const name = ref('Имя');
</script>

<template>
	<h2>Vue</h2>
	<Name :name="name" />
	<Style />
	<List />
	<Counter />
	<h2>TypeSript</h2>
	<Users />
	<Type />
	<Decorator />
	<Merge />
	<Array />
</template>

<style scoped>
</style>
