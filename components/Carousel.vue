<template>
	<v-flex>
		<v-carousel
			cycle
			interval="3000"
			hide-delimiter-background
			show-arrows-on-hover
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
						'https://cdn.vuetifyjs.com/images/cards/docks.jpg',
						'https://cdn.vuetifyjs.com/images/cards/house.jpg'
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