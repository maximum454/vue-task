<template>
	<div>
		<div class="stuff-selected">
			<div class="stuff-selected__item">
				<div class="item-stuff" v-for="item in arrUser" :key="item.id">
					{{ item.name }}
				</div>
				<div class="stuff-selected__num">selected: {{arrUser.length}} / 6</div>
			</div>
			<div class="stuff-selected__item">
				<div class="item-stuff" v-for="item in arrOther" :key="item.id">
					{{ item.name }}
				</div>
			</div>
		</div>
		<div class="stuff">
			<div class="stuff__item">
				<div class="item-stuff" v-for="item in user" :key="item.id" :id="item.id" @click="userSelect">
					{{ item.name }}
				</div>
			</div>
			<div class="stuff__item">
				<div class="item-stuff" v-for="item in other" :key="item.id" :id="item.id" @click="otherSelect">
					{{ item.name }}
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: "TestTask",
	data() {
		return {
			user: [
				{
					"id": 1,
					"name": "Shoes 1"
				},
				{
					"id": 2,
					"name": "Shoes 2"
				},
				{
					"id": 3,
					"name": "Shoes 3"
				},
				{
					"id": 4,
					"name": "Shoes 4"
				},
				{
					"id": 5,
					"name": "T-shirt 1"
				},
				{
					"id": 6,
					"name": "T-shirt 2"
				},
				{
					"id": 7,
					"name": "T-shirt 3"
				},
				{
					"id": 8,
					"name": "T-shirt 4"
				}
			],
			other: [
				{
					"id": 11,
					"name": "Jacket 1"
				},
				{
					"id": 12,
					"name": "Jacket 2"
				},
				{
					"id": 13,
					"name": "Jacket 3"
				},
				{
					"id": 14,
					"name": "Jacket 4"
				},
				{
					"id": 15,
					"name": "Hoodie 1"
				},
				{
					"id": 16,
					"name": "Hoodie 2"
				},
				{
					"id": 17,
					"name": "Hoodie 3"
				},
				{
					"id": 18,
					"name": "Hoodie 4"
				}
			],
			arrUser: [],
			arrOther: [],
			numCount: 5,
		}
	},
	methods: {
		userSelect(e) {
			const idEl = e.target.id
			console.log(idEl)
			this.user.forEach(item => {
				if(item.id === +idEl && this.arrUser.length <= this.numCount){
					this.arrUser.push(item)
				}
			})
		},
		otherSelect(e) {
			const idEl = e.target.id
			this.arrOther = this.other.filter(item => item.id === +idEl);

		}
	},

}
</script>

<style scoped lang="scss">
.stuff {
	display: flex;
	flex-wrap: wrap;
	gap: 40px;
	margin-top: 40px;

	&__item {
		flex: 1 0 calc(50% - 80px);
		max-width: 50%;
		border: 2px solid #000000;
		padding: 20px;
		display: flex;
		flex-wrap: wrap;
		gap: 10px;
		align-items: flex-start;
	}
}

.stuff-selected {
	display: flex;
	flex-wrap: wrap;
	gap: 40px;
	justify-content: space-between;

	&__item {
		flex: 1 0 calc(20% - 80px);
		max-width: 20%;
		border: 2px solid #000000;
		padding: 20px;
		display: flex;
		flex-wrap: wrap;
		gap: 10px;
		align-items: flex-start;
	}
	&__num{
		flex: 1 0 100%;
		text-align: center;
	}
}

.item-stuff {
	border: 2px solid #000000;
	padding: 5px;
	cursor: pointer;
	&:hover{
		background-color: #ccc;
	}
}
</style>