<template>
	<v-flex>
		<v-carousel
			cycle
			interval="3000"
			show-arrows=true
			height="30%"
			hide-delimiters
		>
			<v-carousel-item
				v-for="(src, i) in page.srcs"
				:key="i"
			>
				<img
					:src=src
					height="100%"
					width="100%"
				>
				<p>{{ page.id }}</p>
			</v-carousel-item>
		</v-carousel>
	</v-flex>
</template>

<script>
export default {
	props: ['page-id'],
	data() {
		return {
			id: this.pageId,
			pd: 10,
			pages: [
				{
					title: 1,
					id: 1,
					srcs: [
						require("../assets/3dcads/radio/front.jpg"),
						require("../assets/3dcads/radio/back.jpg"),
					]
				},
				{
					title: 2,
					id: 2,
					srcs: [
						require("../assets/3dcads/kokuyo2019/1.png"),
						require("../assets/3dcads/kokuyo2019/2.png"),
						require("../assets/3dcads/kokuyo2019/3.png"),
					]
				},
				{
					title: 3,
					id: 3,
					srcs: [
						require("../assets/3dcads/tma2022/TangibleAroma.png"),
					]
				},
				{
					title: 4,
					id: 4,
					srcs: [
						require("../assets/3dcads/sndc2024/VLetter.png"),
					]
				},
      ],
		}
	},
  computed: {
    page(){
			return this.pages.find(page => page.id === Number(this.pageId))
		},
  }
}
</script>