<template>
	<v-flex>
		<v-carousel
			cycle
			interval="3000"
			show-arrows=true
			height="30%"
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
						'https://3d-cad.s3.amazonaws.com/Radio/%E3%83%A9%E3%82%B7%E3%82%99%E3%82%AA%E6%AD%A3%E9%9D%A2.jpg',
						'https://3d-cad.s3.amazonaws.com/Radio/%E3%83%A9%E3%82%B7%E3%82%99%E3%82%AA%E8%83%8C%E9%9D%A2.jpg'
					]
				},
				{
					title: 2,
					id: 2,
					srcs: [
						'https://cdn.vuetifyjs.com/images/cards/docks.jpg',
						'https://cdn.vuetifyjs.com/images/cards/house.jpg'
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