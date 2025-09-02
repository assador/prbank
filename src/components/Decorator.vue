<script setup lang="ts">
import { onMounted } from 'vue';

function LogExecutionTime(label?: string) {
	return function <T extends (...args: any[]) => any>(
		value: T,
		context: ClassMethodDecoratorContext
	) {
		const methodName = String(context.name);
		function replacement(this: any, ...args: Parameters<T>): ReturnType<T> {
			const start = performance.now();
			const result = value.apply(this, args);
			const log = (duration: number) => {
				const msg = label
					? `[${label}] метод ${methodName}`
					: `Метод ${methodName}`;
				console.log(`${msg} выполнился за ${duration.toFixed(2)} ms`);
			};
			if (result instanceof Promise) {
				return result.finally(() => {
					const end = performance.now();
					log(end - start);
				}) as ReturnType<T>;
			}
			const end = performance.now();
			log(end - start);
			return result;
		}
		return replacement as T;
	};
}
class Example {
	@LogExecutionTime("Сумма")
	syncFunc(n: number): number {
		let sum = 0;
		for (let i = 0; i < n; i++) {
			sum += i;
		}
		return sum;
	}
	@LogExecutionTime("Асинхронная функция")
	async asyncFunc() {
		return new Promise((resolve) =>
			setTimeout(() => resolve("done"), 300)
		);
	}
}
onMounted(() => {
	const ex = new Example();
	ex.syncFunc(1e6);
	ex.asyncFunc();
});
</script>

<template>
	<h3>3. Простой декоратор метода</h3>
	<p>См. консоль браузера</p>
</template>
