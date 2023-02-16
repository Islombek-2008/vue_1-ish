<template>
	<h1 id="template-title">ONLINE KITOB DO'KONI</h1>
	<nav>
		<div id="right">
			<p>Fall name: {{ fullName }}</p>
			<div v-if="akk" class="akk">
				<p>
					<label for="lastName">Last name</label>
					<input type="text" id="lastName" v-model="lastName" />
				</p>
				<p>
					<label for="firstName">First name</label>
					<input type="text" id="firstName" v-model="firstName" />
				</p>
				<p>
					<label for="fathersName">Father's name</label>
					<input type="text" id="fathersName" v-model="fathersName" />
				</p>
			</div>
			<button @click="akaunt" class="akk-och">
				<span v-if="akk">Yopish</span>
				<span v-else>F.I.SH</span>
			</button>
		</div>
		<span id="border"></span>
		<div id="left">
			<p v-if="bor">
				{{ kitob }}: {{ count }} <br />
				{{ shumBola }}: {{ count1 }}
			</p>
			<button @click="kitobChi">
				<span v-if="bor">Yopish</span>
				<span v-else>Buyurtmalar</span>
				<span id="qoshiluvchi"> {{ count + count1 }}</span>
			</button>
		</div>
	</nav>
	<hr />
	<div id="qidiruv">
		<div id="app">
			<p>O'tgan kunlar {{ count }}</p>
			<button v-on:click="plass">+1</button>
			<button v-on:click="minus">-1</button>
			<button v-on:click="clear">clear</button>
		</div>
		<div id="app2">
			<p>Shum bola {{ count1 }}</p>
			<button v-on:click="plass1">+1</button>
			<button v-on:click="minus1">-1</button>
			<button v-on:click="clear1">clear</button>
		</div>
	</div>
</template>
<script>
export default {
	data() {
		return {
			fathersName: "",
			firstName: "",
			lastName: "",
			akk: true,
			count: 0,
			count1: 0,
			bor: true,
			kitob: "O'tgan konlar",
			shumBola: "Shum bola",
		};
	},
	methods: {
		plass() {
			this.count += 1;
		},
		plass1() {
			this.count1 += 1;
		},
		minus() {
			this.count -= 1;
		},
		minus1() {
			this.count1 -= 1;
		},
		clear() {
			this.count = 0;
		},
		clear1() {
			this.count1 = 0;
		},
		kitobChi() {
			this.bor = !this.bor;
		},
		akaunt() {
			this.akk = !this.akk;
		},
	},
	computed: {
		fullName() {
			return this.lastName + " " + this.firstName + " " + this.fathersName;
		},
	},
};
</script>
<style>
#template-title {
	font-size: 35px;
	color: mediumspringgreen;
}
nav {
	width: 100%;
	display: flex;
	justify-content: space-around;
	align-items: center;
	height: 100px;
}
hr {
	width: 1000px;
	margin-top: 50px;
	margin-bottom: 50px;
}
#border {
	height: 80px;
	width: 1px;
	margin-right: 45px;
	background-color: #000;
}
#right {
	width: 530px;
	height: 100px;
	position: relative;
}
.akk {
	display: flex;
	gap: 15px;
}
.akk-och {
	position: absolute;
	top: 12px;
	right: 10px;
	padding: 5px 10px;
	border: 0;
	color: khaki;
	background-color: dimgrey;
	border-radius: 10px;
}
#left {
	width: 120px;
	height: 50px;
	position: relative;
	display: flex;
	flex-direction: column;
	justify-content: center;
}
#left button {
	position: absolute;
	left: -110px;
	top: -13px;
	color: khaki;
	background-color: dimgrey;
	border-radius: 10px;
	border: 0;
	padding: 5px 10px;
}
#qoshiluvchi {
	color: red;
	font-style: bold;
	margin-left: 5px;
}
#qidiruv {
	margin-top: 50px;
	margin-left: 50px;
}
#qidiruv button {
	margin-left: 15px;
}
</style>
