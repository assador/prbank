<script setup lang="ts">
interface firstInterface {
	number: number;
	string: string;
}
interface secondInterface {
	boolean: boolean;
	null: null;
}

const first: firstInterface = {
	number: 123,
	string: 'абвгд',
};
const second: secondInterface = {
	boolean: true,
	null: null,
};

const merge = (obj1: firstInterface, obj2: secondInterface): any => {
	return { ...obj1, ...obj2 };
};
</script>

<template>
	<h3>4. Функция merge</h3>
	<h4>Первый объект</h4>
	<p>{{ first }}</p>
	<h4>Второй объект</h4>
	<p>{{ second }}</p>
	<h4>Результат</h4>
	<p>{{ merge(first, second) }}</p>
</template>
