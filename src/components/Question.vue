<template>
	<div class="alert">
		<h3>{{x}} + {{y}} = ?</h3>
		<hr>
		<div class="buttons">
			<button class="btn btn-success" v-for="number in answers">
				{{number}}
			</button>
		</div>
	</div>
</template>

<script>
		export default {
		data () {
			return {
				x: mtRand(100, 300), ///рандомное число в интервале 100 - 300
				y: mtRand(100, 500)
			}
		},
		computed: {
			answers() {
				var good = this.x + this.y
				var res = [good];

				while(res.length < 4) {
					var num = mtRand(good - 20, good + 20);//дополняем массив рандомными числами 

					if(res.indexOf(num) === -1) { ///если не содержит такого числа
					res.push(num);
					}

				}
					return res.sort(function(){ ///располагаем значения чисел рандомно для отображения
						return Math.random() > 0.5;
					});

			}

			}
		}
	

	function mtRand(min,max){
		let diff = max - min;
		return Math.floor(Math.random() * (diff + 1)) + min;
	}


</script>

<style>
	.alert {
		padding-top: 20px;
		background-color: #eee;
	}

	.buttons{
		display: flex;
		justify-content: space-around;
	}
</style>