<script setup lang="ts">
defineProps<{ name: string }>();
</script>

<template>
	<h3>1. Простой компонент</h3>
	<p>Привет, {{ name }}</p>
</template>
