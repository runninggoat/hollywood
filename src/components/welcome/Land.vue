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
                <v-flex md4>
                  <v-avatar tile="tile" size="150" style="margin-top: 25rem;">
                    <img :src="require('@/assets/IP-Chain.png')" alt="">
                  </v-avatar>
                  <br/>
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
                        outline=true
                      >
                        <v-icon left dark>add</v-icon>
                        My list
                      </v-btn>
                    </v-flex>
                  </v-layout>
                </v-flex>
              </v-layout>
            </v-img>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </v-app>
</template>

<script>
import SignUp from './SignUp.vue'
import SignIn from './SignIn.vue'
export default {
  components: {
    SignUp,
    SignIn,
  },
  data () {
    return {
      displayOpt: 0,
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

