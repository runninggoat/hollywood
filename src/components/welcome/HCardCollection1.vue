<template>
  <!-- this horizontal card collection style 1 is for static card, the text and icon overlap on the image -->
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

    <!-- take up some place in case of the overlap of the left button -->
    <v-flex>
      <v-card color="transparent" height="1" width="100" style="display: inline-block;"></v-card>
    </v-flex>

    <!-- this horizontal scrollable card collection is made up of many cards, each one has this structure -->
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
            :src="item.staticSrc"
          >
            <v-container fluid fill-height v-show="hover" class="pa-0">
              <v-layout row wrap align-end justify-start fill-height>
                <v-flex xs12 align-start class="text-md-left">
                  <div class="pa-3" style="background-color: #000000; opacity: 0.6; white-space: normal;">
                    <div class="headline" style="overflow: hidden; text-overflow: ellipsis; display: -webkit-box; -webkit-line-clamp: 1; -webkit-box-orient: vertical;">{{ item.title }}</div>
                    <div class="body-2 mb-1" style="overflow: hidden; text-overflow: ellipsis; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical;">{{ item.description }}</div>
                    <v-icon @click=";">play_circle_outline</v-icon>
                  </div>
                </v-flex>
              </v-layout>
            </v-container>
          </v-img>
        </v-card>
      </v-hover>
    </v-flex>

    <!-- take up some place in case of the overlap of the right button -->
    <v-flex>
      <v-card color="transparent" height="1" width="200" style="display: inline-block;"></v-card>
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
        {
          staticSrc: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
          hoverSrc: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
          title: '多親是曾他',
          description: '動戰發文自喜深所麼市，爭醫化境往只三趣同把論一答的你想：冷的大須以山從手客好常中投部參有講心，手定在以必，總登查立了我良裡是說各旅有人法案，會層天花！絕山希父實智集首成麼名據、過單不爸將然設物，走引市：況有們。',
        },
        {
          staticSrc: 'https://jooinn.com/images1280_/mountain-27.jpg',
          hoverSrc: 'https://jooinn.com/images1280_/mountain-27.jpg',
          title: 'Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla mattis consequat nibh, at vulputate nibh commodo ut. Phasellus bibendum magna in tellus sodales fermentum. Proin malesuada sem eget sem gravida tristique. Sed a ligula commodo, condimentum nibh quis, tincidunt felis. Sed efficitur, nisi id eleifend eleifend, augue diam porta purus, in facilisis ipsum tellus a tortor. Donec non pulvinar nulla. Proin et lacus maximus, efficitur neque sed, sodales dui.',
        },
        {
          staticSrc: 'https://jooinn.com/images1280_/mountain-8.jpg',
          hoverSrc: 'https://jooinn.com/images1280_/mountain-8.jpg',
          title: '定星公民書氣出且看能接顧用人',
          description: '外例國一用展李個有天代再苦舉感新力……阿精後如國票色夫地政友的到聲是到動望笑覺去明。的戰點畫氣命重度集是青邊先色理、力度度寫本好好前港西金南開很車老我作如座族你家孩為戰一客只那十古管會態把！作讀告友風失進進師人這動。',
        },
        {
          staticSrc: 'https://jooinn.com/images1280_/mountain-100.jpg',
          hoverSrc: 'https://jooinn.com/images1280_/mountain-100.jpg',
          title: '委出國這會士只班應的明人位',
          description: '如決品國此入開！一這新是立理毒在上詩訴，男識目界著事；風小海男一小，旅指學有格約樣鄉靈十分傳。中話致結縣讓身現許臺，法心成乎五麼大處辦出進不專無和法……上會遊展！勢切怕初熱必得來建興看層子大愛溫此木連大你準也動研行他前推微自受不好。',
        },
        {
          staticSrc: 'https://jooinn.com/images1280_/mountain-106.jpg',
          hoverSrc: 'https://jooinn.com/images1280_/mountain-106.jpg',
          title: '令心法走家評社大情',
          description: '高政自大的男好在加生法一得似過保臉廠些了爭與……面藝學法計然次性品紙定能總手故天問。南了發東理……讀此然我視風什化子且動加，團入手面流於人選第？足頭汽得……雲洲直們業的少代錯檢然是那料小名天原職投度以出生告千來怕心子看。',
        },
        {
          staticSrc: 'https://jooinn.com/images1280_/mountain-102.jpg',
          hoverSrc: 'https://jooinn.com/images1280_/mountain-102.jpg',
          title: 'Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla mattis consequat nibh, at vulputate nibh commodo ut. Phasellus bibendum magna in tellus sodales fermentum. Proin malesuada sem eget sem gravida tristique. Sed a ligula commodo, condimentum nibh quis, tincidunt felis. Sed efficitur, nisi id eleifend eleifend, augue diam porta purus, in facilisis ipsum tellus a tortor. Donec non pulvinar nulla. Proin et lacus maximus, efficitur neque sed, sodales dui.',
        },
        {
          staticSrc: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
          hoverSrc: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
          title: 'Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla mattis consequat nibh, at vulputate nibh commodo ut. Phasellus bibendum magna in tellus sodales fermentum. Proin malesuada sem eget sem gravida tristique. Sed a ligula commodo, condimentum nibh quis, tincidunt felis. Sed efficitur, nisi id eleifend eleifend, augue diam porta purus, in facilisis ipsum tellus a tortor. Donec non pulvinar nulla. Proin et lacus maximus, efficitur neque sed, sodales dui.',
        },
        {
          staticSrc: 'https://jooinn.com/images1280_/mountain-10.jpg',
          hoverSrc: 'https://jooinn.com/images1280_/mountain-10.jpg',
          title: 'Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla mattis consequat nibh, at vulputate nibh commodo ut. Phasellus bibendum magna in tellus sodales fermentum. Proin malesuada sem eget sem gravida tristique. Sed a ligula commodo, condimentum nibh quis, tincidunt felis. Sed efficitur, nisi id eleifend eleifend, augue diam porta purus, in facilisis ipsum tellus a tortor. Donec non pulvinar nulla. Proin et lacus maximus, efficitur neque sed, sodales dui.',
        },
        {
          staticSrc: 'https://jooinn.com/images1280_/green-mountain-1.jpg',
          hoverSrc: 'https://jooinn.com/images1280_/green-mountain-1.jpg',
          title: 'Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla mattis consequat nibh, at vulputate nibh commodo ut. Phasellus bibendum magna in tellus sodales fermentum. Proin malesuada sem eget sem gravida tristique. Sed a ligula commodo, condimentum nibh quis, tincidunt felis. Sed efficitur, nisi id eleifend eleifend, augue diam porta purus, in facilisis ipsum tellus a tortor. Donec non pulvinar nulla. Proin et lacus maximus, efficitur neque sed, sodales dui.',
        },
        {
          staticSrc: 'https://jooinn.com/images/mountain-103.jpg',
          hoverSrc: 'https://jooinn.com/images/mountain-103.jpg',
          title: 'Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla mattis consequat nibh, at vulputate nibh commodo ut. Phasellus bibendum magna in tellus sodales fermentum. Proin malesuada sem eget sem gravida tristique. Sed a ligula commodo, condimentum nibh quis, tincidunt felis. Sed efficitur, nisi id eleifend eleifend, augue diam porta purus, in facilisis ipsum tellus a tortor. Donec non pulvinar nulla. Proin et lacus maximus, efficitur neque sed, sodales dui.',
        },
        {
          staticSrc: 'http://n8m4f3g2l3720eoav2dcrd31.wpengine.netdna-cdn.com/wp-content/uploads/2016/12/Fire-sunset.jpg',
          hoverSrc: 'http://n8m4f3g2l3720eoav2dcrd31.wpengine.netdna-cdn.com/wp-content/uploads/2016/12/Fire-sunset.jpg',
          title: 'Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla mattis consequat nibh, at vulputate nibh commodo ut. Phasellus bibendum magna in tellus sodales fermentum. Proin malesuada sem eget sem gravida tristique. Sed a ligula commodo, condimentum nibh quis, tincidunt felis. Sed efficitur, nisi id eleifend eleifend, augue diam porta purus, in facilisis ipsum tellus a tortor. Donec non pulvinar nulla. Proin et lacus maximus, efficitur neque sed, sodales dui.',
        },
        {
          staticSrc: 'https://png.pngtree.com/thumb_back/fw800/back_pic/03/66/23/4557afff1960d99.jpg',
          hoverSrc: 'https://png.pngtree.com/thumb_back/fw800/back_pic/03/66/23/4557afff1960d99.jpg',
          title: 'Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla mattis consequat nibh, at vulputate nibh commodo ut. Phasellus bibendum magna in tellus sodales fermentum. Proin malesuada sem eget sem gravida tristique. Sed a ligula commodo, condimentum nibh quis, tincidunt felis. Sed efficitur, nisi id eleifend eleifend, augue diam porta purus, in facilisis ipsum tellus a tortor. Donec non pulvinar nulla. Proin et lacus maximus, efficitur neque sed, sodales dui.',
        },
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
