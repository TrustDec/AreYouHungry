<template>
	<div class="header">
		<div class="content-wrapper">
			<div class="avatar">
				<img :src="seller.avatar" width="64">
			</div>
			<div class="content">
				<div class="title">
					<span class="brand"></span>
					<span class="name">{{seller.name}}</span>
				</div>
				<div class="description">
					{{seller.description}}/{{seller.deliveryTime}}分钟送达
				</div>
				<div v-if="seller.supports" class="supports">
					<span class="icon"></span>
					<span class="text">{{seller.supports[0].description}}</span>
				</div>
			</div>
		</div>
		<div class="bulletin-wrapper"></div>
	</div>
</template>

<script type="text/ecmascript-6">
	export default {
		props: {
			seller: {
				type: Object
			}
		}
	};
</script>

<style lang="stylus" rel="stylesheet/stylus">
	 @import "../../common/stylus/mixin";
	
	.header
		color: #fff
		background-color: #000
		.content-wrapper
			padding: 24px 12px 18px 24px;
			font-size: 0
			.avatar
				display: inline-block
			.content
				display: inline-block
				margin-left: 16px
				font-size: 16px
				.title
					margin: 2px 0 8px 0
					.brand
						width: 30px
						height: 18px
						display: inline-block
						vertical-align: top
						bg-image('brand')
						background-size: 30px 18px
						background-repeat: no-repeat
					.name
						margin-left: 6px
						font-size: 16px
						line-height: 18px
						font-weight: bold
</style>