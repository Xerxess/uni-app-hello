<template>
	<view>
		<page-head :title="title"></page-head>
		<view class="uni-common-mt">
			<view>
				<map id="mymap" :latitude="latitude" :longitude="longitude" :markers="covers" :show-location="true">
				</map>
			</view>
			<button @click="moveToLocation" style="position: ;">返回当前中心位置</button>
			<button @click="includePoints">展示所点</button>
			<canvas style="width: 300px; height: 200px;" canvas-id="firstCanvas"></canvas>
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				title: 'map',
				myMap: null,
				latitude: 29.526882,
				longitude: 106.488483,
				covers: [{
					latitude: 29.532744,
					longitude: 106.484749,
					// #ifdef APP-PLUS
					iconPath: '../../../static/app-plus/location@3x.png',
					// #endif
					// #ifndef APP-PLUS
					iconPath: '../../../static/location.png',
					// #endif
				}, {
					latitude: 29.520197,
					longitude: 106.496293,
					// #ifdef APP-PLUS
					iconPath: '../../../static/app-plus/location@3x.png',
					// #endif
					// #ifndef APP-PLUS
					iconPath: '../../../static/location.png',
					// #endif
				}]
			}
		},
		onReady: function (e) {
        var context = uni.createCanvasContext('firstCanvas')

        context.setStrokeStyle("#00ff00")
        context.setLineWidth(5)
        context.rect(0, 0, 200, 200)
        context.stroke()
        context.setStrokeStyle("#ff0000")
        context.setLineWidth(2)
        context.moveTo(160, 100)
        context.arc(100, 100, 60, 0, 2 * Math.PI, true)
        context.moveTo(140, 100)
        context.arc(100, 100, 40, 0, Math.PI, false)
        context.moveTo(85, 80)
        context.arc(80, 80, 5, 0, 2 * Math.PI, true)
        context.moveTo(125, 80)
        context.arc(120, 80, 5, 0, 2 * Math.PI, true)
        context.stroke()
        context.draw()
    },
		onLoad() {
			this.myMap = uni.createMapContext('mymap', this)
		},
		methods: {
			moveToLocation() {
				this.myMap.moveToLocation()
			},
			moveToLocation2() {
				this.longitude=120
				this.covers[0].latitude=45
			},
			includePoints(){
				this.myMap.includePoints({
					points:[
						{latitude:29.520197,longitude:106.496293},
						{latitude:29.532744,longitude:106.484749}
					]
				});
			}
		}
	}
</script>
<style>
	map {
		width: 100%;
		height: 600upx;
	}
</style>
