<template>
  <v-app dark>
    <v-container fluid class="pa-0">
      <v-layout row wrap>
        <v-flex md12>
          <v-card>
            <v-img
              :aspect-ratio="20/9"
              src="https://jooinn.com/images1280_/mountain-27.jpg"
            >
              <v-toolbar
                fixed
                dark
                flat
                style="opacity: 0.8;"
              >
                <v-avatar tile="tile" size="36">
                  <img :src="require('@/assets/IP-Chain.png')" alt="" >
                </v-avatar>
                &nbsp;&nbsp;
                <span
                  class="headline red--text"
                >HollyWood Chain</span>
                <v-spacer></v-spacer>
                <v-text-field
                  flat
                  dark
                  color="white"
                  background-color="transparent"
                  clearable
                  clear-icon="cancel"
                  placeholder="Search for your interest"
                  :append-icon="'search'"
                  @click:append="search"
                ></v-text-field>
                <v-toolbar-items>
                  <v-btn
                    flat
                  >Sign In</v-btn>
                  <v-btn
                    flat
                  >Sign Up</v-btn>
                  <v-btn
                    flat
                  >Forgot Password</v-btn>
                  <v-btn
                    flat
                  >Help</v-btn>
                  <v-btn
                    flat
                  >Contact</v-btn>
                </v-toolbar-items>
              </v-toolbar>
              <v-layout row wrap>
                <v-flex xs8 sm8 md6 lg5 xl4>
                  <div style="margin-top: 25rem;"></div>
                  <div class="display-2">HollyWood Chain</div>
                  <br/>
                  <v-layout justify-center>
                    <v-flex md8>
                      <div class="headline">Welcome to HollyWood Chain. HollyWood Chain is an open platform which is using blockchain and IPFS file system for video sharing. Join us to let your idea viewed by the global.</div>
                    </v-flex>
                  </v-layout>
                  <v-layout justify-center>
                    <v-flex md6>
                      <v-btn
                        dark
                        color="red"
                      >
                        <v-icon left dark>play_arrow</v-icon>
                        Play
                      </v-btn>
                      <v-btn
                        dark
                        color="white"
                        :outline="true"
                      >
                        <v-icon left dark>add</v-icon>
                        My list
                      </v-btn>
                    </v-flex>
                  </v-layout>
                  <div style="margin-bottom: 5rem;"></div>
                </v-flex>
              </v-layout>
            </v-img>
          </v-card>
        </v-flex>
      </v-layout>
      <!-- card collections -->
      <h-card-collection1></h-card-collection1>
      <h-card-collection2></h-card-collection2>
      <!-- footer -->
      <v-footer
        dark
        height="auto"
      >
        <v-card
          class="flex"
          flat
          tile
        >
          <v-card-title class="gray">
            <strong class="subheading">Get connected with us on HollyWood Chain!</strong>
            <v-spacer></v-spacer>
            <v-btn
              v-for="icon in icons"
              :key="icon"
              class="mx-3"
              dark
              icon
            >
              <v-icon size="24px">{{ icon }}</v-icon>
            </v-btn>
          </v-card-title>
          <v-card-actions class="grey darken-3 justify-center">
            &copy;2018 — <strong>HollyWood Chain</strong>
          </v-card-actions>
        </v-card>
      </v-footer>
    </v-container>
  </v-app>
</template>

<script>
import HCardCollection1 from './HCardCollection1'
import HCardCollection2 from './HCardCollection2'
export default {
  components: {
    HCardCollection1,
    HCardCollection2,
  },
  data () {
    return {
      displayOpt: 0,
      icons: [
        'drafts',
        'contact_mail',
        'phone',
        'android',
        'g_translate'
      ],
    }
  },
  create () {
    this.$i18n.locale = 'zh'
  },
  methods: {
    search () {
      console.log('search...')
    },
  },
}
</script>

