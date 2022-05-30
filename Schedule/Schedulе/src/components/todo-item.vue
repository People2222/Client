<template>
	<tr class="table">
		<td>{{park.object}}</td>
		<td>{{park.adress}}</td>
		<td>
			<button @click="toggleModal">Просмотр</button>
			<Modal :scrollable="true" v-show="isShowModal" :show="isShowModal" @close="toggleModal">
				<template #header>
					<div>Парковочная зона</div>
				</template>
				<template #body>
					<div><b>Объект:</b> {{park.object}}</div>
					<div><b>Адрес:</b> {{park.adress}}</div>
					<br>
					<div><b>Количество парковочных мест:</b> {{park.kolvo}}</div>
					<br>
					<img src="src/logo/1.png" style="width: 100%; margin-bottom: 10px">
				</template>
			</Modal>
		</td>
		<td><button v-on:click="$emit('remove')">Удалить</button></td>
	</tr>
</template>

<script>
import Modal from 'C://Users//Дарья//Desktop//dec//123//Schedule — копия — копия//src//components//modal-window.vue';

export default {
	props: ["park"],
	components: {
		Modal
	},
	methods: {
		toggleModal() {
			this.isShowModal = !this.isShowModal;
		},
	},
	data() {
		return {
			isShowModal: false,
		}
	}
}
</script>

<style scoped>

td {
	padding: 5px;
	border: none;
	border-bottom: 5px solid #F2F8F8;
}
.table {
	width: 100%;
	margin-bottom: 20px;
	border: 15px solid #F2F8F8;
	border-top: 5px solid #F2F8F8;
	border-collapse: collapse;
}
</style>
