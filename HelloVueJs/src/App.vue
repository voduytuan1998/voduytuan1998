<template>
	<div id="app">
		        <div class="wrapper clearfix">
				<players
					v-bind:scorePlayer="scorePlayer"
					v-bind:activePlayer="activePlayer"
					v-bind:curentScore="curentScore"
				/>
				<control
					v-on:handerNewGame="handerNewGame"
				/>
				<dice/>
        </div>
		<popup-rule/>
	</div>
</template>

<script>
import Control from './components/Control.vue'
import Dice from './components/Dice.vue'
import Players from './components/Players.vue'
import PopupRule from './components/popupRule.vue'

export default {
	name: 'app',
	data () {
		return {
			activePlayer:1,
			scorePlayer:[13,30],
			curentScore:2
		}
	},
	methods:{
		handerNewGame(){
			console.log('handerNewGame App.vue')
		}
	},
	components: {
		Players,
		Control,
		Dice,
		PopupRule
	}
}
</script>

<style>
	* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    
}

.clearfix::after {
    content: "";
    display: table;
    clear: both;
}

body {
    background-image: linear-gradient(rgba(62, 20, 20, 0.4), rgba(62, 20, 20, 0.4)), url('/public/assets/back.jpg');
    background-size: cover;
    background-position: center;
    font-family: Lato;
    font-weight: 300;
    position: relative;
    height: 100vh;
    color: #555;
}

.wrapper {
    width: 1000px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: #fff;
    box-shadow: 0px 10px 50px rgba(0, 0, 0, 0.3);
    overflow: hidden;
}






</style>
