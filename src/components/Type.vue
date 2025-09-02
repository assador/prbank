<script setup lang="ts">

type ResponseType<T> = T extends object ? T : null;

// Объект остаётся объектом
// @ts-ignore: unused variable
type A = ResponseType<{ id: number; name: string }>;
// A = { id: number; name: string }
// Массив (тоже объект) остаётся массивом
// @ts-ignore: unused variable
type B = ResponseType<string[]>;
// B = string[]

// null или undefined не объект, возвращает null
// @ts-ignore: unused variable
type C = ResponseType<null>;
// C = null
// @ts-ignore: unused variable
type D = ResponseType<undefined>;
// D = null

// Примитивы превращаются в null
// @ts-ignore: unused variable
type E = ResponseType<string>;
// E = null
// @ts-ignore: unused variable
type F = ResponseType<number>;
// F = null
// @ts-ignore: unused variable
type G = ResponseType<boolean>;
// G = null

// Функции тоже объекты в TS, остаются функцией
// @ts-ignore: unused variable
type H = ResponseType<() => void>;
// H = () => void

</script>

<template>
	<h3>2. Условный тип</h3>
	<p>Примеры в коде компонента /src/components/Type.vue</p>
</template>
