<script setup lang="ts">
interface User {
	id: number;
	name: string;
	email: string;
	isActive: boolean;
}

const usersExample:User[] = [
	{
		id: 1,
		name: 'Ваня',
		email: 'vanya@host.com',
		isActive: false,
	}, {
		id: 2,
		name: 'Маша',
		email: 'masha@host.com',
		isActive: true,
	}, {
		id: 3,
		name: 'Витя',
		email: 'vitya@host.com',
		isActive: false,
	}, {
		id: 4,
		name: 'Васисуалий',
		email: 'vasisualy@host.com',
		isActive: true,
	},
];
const onlyActive = (users: User[]): User[] => {
	return users.filter((user: User) => user.isActive);
}
</script>

<template>
	<h3>1. Интерфейс для описания объекта пользователя</h3>
	<h4>Все пользователи</h4>
	<ul>
		<li v-for="user of usersExample">
			<div>id: {{ user.id }}</div>
			<div>name: {{ user.name }}</div>
			<div>email: {{ user.email }}</div>
			<div>isActive: {{ user.isActive }}</div>
		</li>
	</ul>
	<h4>Только активные пользователи</h4>
	<ul>
		<li v-for="user of onlyActive(usersExample)">
			<div>id: {{ user.id }}</div>
			<div>name: {{ user.name }}</div>
			<div>email: {{ user.email }}</div>
			<div>isActive: {{ user.isActive }}</div>
		</li>
	</ul>
</template>
