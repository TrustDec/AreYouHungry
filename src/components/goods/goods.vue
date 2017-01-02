<template>
	<div class="goods">
		<div class="menu-wrapper">
			<ul>
				<li v-for="item in goods">
					<span class="text">
						<span v-show="item.type>0" class="icon" :class="classMap[item.type]"></span>
						{{item.name}}
					</span>
				</li>
			</ul>
		</div>
		<div class="foods-wrapper"></div>		
	</div>
</template>

<script type="text/ecmas cript-6">
const ERR_OK = 0;
	export default {
		props: {
			seller: {
				type: Object
			}
		},
		data() {
			return {
				goods: []
			};
		},
		created() {
			this.classMap = ['decrease', 'discount', 'special', 'invoice', 'guarantee'];
			this.$http.get('/api/goods').then((response) => {
				console.log(response);
				response = response.body;
				if (response.errno === ERR_OK) {
					this.goods = response.data;
					console.log(this.goods);
				}
			});
		}
	};
</script>

<style lang="stylus" rel="stylesheet/stylus">
	.goods
		display: flex
		position: absolute
		width: 100%
		top: 174px
		bottom: 46px
		overflow: hidden
		.menu-wrapper
			flex: 0 0 80px
			width: 80px
			background: #f3f5f7
		.foods-wrapper
			flex: 1
</style>