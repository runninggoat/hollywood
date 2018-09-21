<template>
  <v-layout row nowrap pt-4 pb-4
    style="margin-top: 50px; overflow-x: scroll; overflow-y: hidden; white-space: nowrap;"
  >
    <v-btn
      color="gray"
      dark
      large
      absolute
      left
      fab
      style="margin-top: 50px;"
      @click="scrollLeft"
    >
      <v-icon>keyboard_arrow_left</v-icon>
    </v-btn>
    <v-flex
      v-for="(item, i) in cards"
      :key="i"
      style="display: inline-block;"
    >
      <v-hover>
        <v-card
          flat
          slot-scope="{ hover }"
          :class="`elevation-${hover ? 12 : 0}`"
          class="mx-auto"
          height="200"
          :width="hover ? '400' : '300'"
          color="transparent"
          :style="{ marginTop: hover ? '-30px' : '0px' }"
        >
          <v-img
            :aspect-ratio="16/9"
            :src="item"
          ></v-img>
        </v-card>
      </v-hover>
    </v-flex>
    <v-btn
      color="gray"
      dark
      large
      absolute
      right
      fab
      style="margin-top: 50px;"
      @click="scrollRight"
    >
      <v-icon>keyboard_arrow_right</v-icon>
    </v-btn>
  </v-layout>
</template>

<script>
export default {
  data () {
    return {
      cards: [
        'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        'https://jooinn.com/images1280_/mountain-27.jpg',
        'https://jooinn.com/images1280_/mountain-8.jpg',
        'https://jooinn.com/images1280_/mountain-100.jpg',
        'https://jooinn.com/images1280_/mountain-106.jpg',
        'https://jooinn.com/images1280_/mountain-102.jpg',
        'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        'https://jooinn.com/images1280_/mountain-10.jpg',
        'https://jooinn.com/images1280_/green-mountain-1.jpg',
        'https://jooinn.com/images/mountain-103.jpg',
        'http://n8m4f3g2l3720eoav2dcrd31.wpengine.netdna-cdn.com/wp-content/uploads/2016/12/Fire-sunset.jpg',
        'https://png.pngtree.com/thumb_back/fw800/back_pic/03/66/23/4557afff1960d99.jpg',
      ],
      speed: 10,
    }
  },
  methods: {
    scrollRight () {
      var scrollAmount = 0
      var slideTimer = setInterval(() => {
        this.$el.scrollLeft += 10
        scrollAmount += 10
        if (scrollAmount >= 300) {
          window.clearInterval(slideTimer)
        }
      }, 10)
    },
    scrollLeft () {
      var scrollAmount = 0
      var slideTimer = setInterval(() => {
        this.$el.scrollLeft -= 10
        scrollAmount += 10
        if (scrollAmount >= 300) {
          window.clearInterval(slideTimer)
        }
      }, 10)
    },
  },
}
</script>
