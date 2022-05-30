<template>
	<div class="back">
		<div class="logo"> <img src="src/logo/logo.png"> </div>
		<div class="content">
	 <button id="back" class="btn"><a href="HomeAdmin">Назад</a></button>

			<table class="table">
				<thead>
				<tr>
					<th class="column fio" style="width: 35%">ФИО</th>
					<th class="column number" style="width: 15%">Гос. номер</th>
					<th class="column place" style="width: 25%">Объект КФУ</th>
					<th class="column status" style="width: 15%">Статус</th>
					<th class="column status" style="width: 10%"></th>
				</tr>
				</thead>
				<tbody>

				<tr
					is="listOfApplAdmin"
					v-for="appl in applications"
					v-bind:application="appl"
					:onLogin='onLogin'
					></tr>

				</tbody>
			</table>
			<br><br>
			<div class="footer">© 2022 Федеральное государственное автономное образовательное учреждение высшего образования "Казанский (Приволжский) федеральный университет"</div>
		</div>
	</div>
</template>

<script>
import Modal from 'C://Users//Дарья//Desktop//dec//123//Schedule — копия — копия//src//components//modal-window.vue';
import listOfApplAdmin from "../../components/listOfApplAdmin";

export default {
	components: {
		Modal, listOfApplAdmin
	},
	data() {
		return {
			isShowModal: false,
			applications: [
				{
					id: "0001",
					fio: 'Иванов Сергей Михайлович',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'А200РО121',
					color: 'черный',
					fio_vlad: 'Попов Кирилл Витальевич',
					object: 'Второе учебное здание',
					status: 'Одобрено'
				},
				{
					id: "0002",
					fio: 'Попов Кирилл Витальевич',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'Л250ИК16',
					color: 'черный',
					fio_vlad: 'Попов Кирилл Витальевич',
					object: 'Второе учебное здание',
					status: 'Одобрено'
				},
				{
					id: "0003",
					fio: 'Илларионов Михаил Прокопьевич',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'Л899ЛВ116',
					color: 'черный',
					fio_vlad: 'Попов Кирилл Витальевич',
					object: 'Главное здание',
					status: 'Одобрено'
				},
				{
					id: "0004",
					fio: 'Петрова Юлия Максимовна',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'К566РЛ116',
					color: 'черный',
					fio_vlad: 'Попов Кирилл Витальевич',
					object: 'Главное здание',
					status: 'На рассмотрении'
				},
				{
					id: "0005",
					fio: 'Еремин Михаил Матвеевич',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'А152ЕЕ16',
					color: 'черный',
					fio_vlad: 'Попов Кирилл Витальевич',
					object: 'Второе учебное здание',
					status: 'Отказано'
				},
				{
					id: "0006",
					fio: 'Крылов Владимир Романович',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'К415ТО116',
					color: 'черный',
					fio_vlad: 'Попов Кирилл Витальевич',
					object: 'Нужина 1/7',
					status: 'Одобрено'
				},
				{
					id: "0007",
					fio: 'Лавров Платон Дмитриевич',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'Н131МХ16',
					color: 'черный',
					fio_vlad: 'Попов Кирилл Витальевич',
					object: 'Главное здание',
					status: 'Одобрено'
				},
				{
					id: "0008",
					fio: 'Успенский Лев Никитич',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'С300ОЕ63',
					color: 'черный',
					fio_vlad: 'Попов Кирилл Витальевич',
					object: 'Второе учебное здание',
					status: 'Одобрено'
				},
				{
					id: "0009",
					fio: 'Фадеев Артемий Арсенович',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'К366УВ116',
					color: 'черный',
					fio_vlad: 'Попов Кирилл Витальевич',
					object: 'Нужина 1/7',
					status: 'Одобрено'
				},
				{
					id: "0010",
					fio: 'Климов Арсений Платонович',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'С900ЕО16',
					color: 'черный',
					fio_vlad: 'Попов Кирилл Витальевич',
					object: 'Второе учебное здание',
					status: 'Одобрено'
				},
				{
					id: "0011",
					fio: 'Шубин Дмитрий Тимофеевич',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'А449ТA21',
					color: 'черный',
					fio_vlad: 'Попов Кирилл Витальевич',
					object: 'Нужина 1/7',
					status: 'На рассмотрении'
				},
				{
					id: "0012",
					fio: 'Меркулов Артём Тимофеевич',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'К621КТ716',
					color: 'черный',
					fio_vlad: 'Попов Кирилл Витальевич',
					object: 'Главное здание',
					status: 'Одобрено'
				},
				{
					id: "0013",
					fio: 'Марков Григорий Павлович',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'К341ЕС116',
					color: 'черный',
					fio_vlad: 'Попов Кирилл Витальевич',
					object: 'Главное здание',
					status: 'Одобрено'
				},
				{
					id: "0014",
					fio: 'Иванов Сергей Михайлович',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'К341ЕС116',
					color: 'черный',
					fio_vlad: 'Иванов Сергей Михайлович',
					object: 'Главное здание',
					status: 'Отказано'
				},
				{
					id: "0015",
					fio: 'Иванов Сергей Михайлович',
					podrazd: 'Департамент охраны',
					doljn: 'Охранник',
					tel: '89613448868',
					marka: 'KIA',
					model: 'Seed',
					nomer: 'А200РО121',
					color: 'черный',
					fio_vlad: 'Иванов Сергей Михайлович',
					object: 'Нужина 1/7',
					status: 'На рассмотрении'
				}
			]
		}
	},
	methods: {
		toggleModal() {
			this.isShowModal = !this.isShowModal;
		},
		addNewTodo: function () {
			this.parking.push({
				object: this.newObject,
				adress: this.newAdress,
				kolvo: this.newKolvo,
			})
			this.newObject = ''
			this.newAdress = ''
			this.newKolvo = ''
		},
			onLogin (data) {
				/*console.log('child component said login', data)*/
				Vue.set(this.applications, this.appl, )
			}
		}

};
</script>

<style scoped>
.button {
	-webkit-transition: box-shadow 300ms ease-in-out, color 300ms ease-in-out;
	transition: box-shadow 300ms ease-in-out, color 300ms ease-in-out;
}
.button:hover {
	box-shadow: 0 0 40px 40px rgba(70,130,210,0.6) inset;
}

.back{
	width: 100%;
	height: 90px;
	background: #005590;
	position: absolute;
	top: 0px;
	left: 0px;
}
.chapter{
	border:  2px solid #0a68b4;
	padding: 10px 15px;
	font-size: 18px;
	margin-top: 20px;
	width: 60%;
	margin-left: auto;
	margin-right: auto;
	color: black;
}
.content{
	width: 75%;
	margin-left: auto;
	margin-right: auto;
}

.btn{
	color: white;
	font-weight: revert;
	text-decoration: none;
	width: 10%;
	border: 2px solid #0a68b4;
	padding: 3px 20px;
	margin: 15px;
	margin-top: 10px;
	margin-left: 0px;
	border-radius: 2px;
	font-size: 12px;;
	font-family: 'Montserrat', sans-serif;
	text-transform: uppercase;
	letter-spacing: 2px;
	background-image: linear-gradient(to right, #005fa0 0%, #4169E1 51%, #0000CD 100%);
	background-size: 200% auto;
	box-shadow: 0 0 20px rgba(0, 0, 0, .1);
	transition: .5s;
}
.table {
	width: 100%;
	margin-bottom: 20px;
	border: 15px solid #F2F8F8;
	border-top: 5px solid #F2F8F8;
	border-collapse: collapse;
}
.table th {
	font-weight: bold;
	padding: 8px;
	background: #F2F8F8;
	border: none;
	border-bottom: 5px solid #F2F8F8;
}
.table td {
	padding: 5px;
	border: none;
	border-bottom: 5px solid #F2F8F8;
}
#scroll{
	overflow-y: auto;
}
.footer{
	position: fixed; /* Фиксированное положение */
	left: 0; bottom: 0; /* Левый нижний угол */
	padding: 8px; /* Поля вокруг текста */
	background: #4682b4; /* Цвет фона */
//color: #005590; /* Цвет текста */
	width: 100%; /* Ширина слоя */
	text-align: center;
	color: whitesmoke;
}
a{
	color:white;
}
.buttonRow{
	width: 70%;
	margin: 20px 15% 5px;
}
table{
	margin-bottom: 50px;
}

</style>
