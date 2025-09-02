<script setup lang="ts">
function isArray<T>(arg: unknown): arg is T[] {
	return Array.isArray(arg);
}
function length(value: string | string[]) {
	if (isArray<string>(value)) {
		return (value + ': массив строк, длина: ' + value.length);
	} else {
		return (value + ': обычная строка, длина: ' + value.length);
	}
}
</script>

<template>
	<h3>5. Функция isArray</h3>
	<p>{{ length("Словечко") }}</p>
	<p>{{ length(['А', 'Б', 'В']) }}</p>
</template>
