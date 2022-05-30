<template>
	<tr>
		<td>{{ application.fio }}</td>
		<td>{{ application.nomer }}</td>
		<td>{{ application.object }}</td>
		<td>{{ application.status }}</td>
		<td>
			<button @click="toggleModal">Просмотр</button>
			<Modal :scrollable="true" v-show="isShowModal" :show="isShowModal" @close="toggleModal">
				<template #header>
					<div>Заявление №{{application.id}}</div>
				</template>
				<template #body>
					<div><b>ФИО:</b> {{ application.fio }}</div>
					<div><b>Структурное подразделение:</b> {{ application.podrazd }}</div>
					<div><b>Должность:</b> {{application.doljn}}</div>
					<div><b>Телефон:</b> {{ application.tel }}</div>
					<br>
					<div><b>Марка автомобиля:</b> {{application.marka}}</div>
					<div><b>Модель:</b> {{ application.model }}</div>
					<div><b>Гос. номер:</b> {{ application.nomer }}</div>
					<div><b>Цвет автомобиля:</b> {{ application.color }}</div>
					<div><b>ФИО владельца:</b> {{ application.fio_vlad }}</div>
					<br>
					<div><b>Объект КФУ:</b> {{application.object}}</div>
					<div><b>Текущий статус:</b> {{ application.status }}</div>

					<div class="buttonRow"><button type="button" v-model="statuss" class="button" style="margin-right: 5px" @click="toggleModal">
						Одобрить
					</button>
						<button type="button" class="button" v-model="statuss" style="margin-right: 5px" @click="toggleModal">
							На рассмотрение
						</button>
						<button type="button" class="button" v-model="statuss" @click="toggleModal">
							Отклонить
						</button>
					</div>
				</template>
			</Modal>
		</td>
	</tr>
</template>

<script>
import Modal from 'C://Users//Дарья//Desktop//dec//123//Schedule — копия — копия//src//components//modal-window.vue';

export default {
	props: ["application", 'onLogin'],
	components: {
		Modal
	},
	methods: {
		toggleModal() {
			this.isShowModal = !this.isShowModal;
		},
		login () {
			this.onLogin({
				email: this.email,
				password: this.password
			})
		}
	},
	data() {
		return {
			isShowModal: false,
			statuss: this.statuss
		}

	},
}
</script>

<style scoped>

</style>
