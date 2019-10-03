<template>
  <v-container fluid id="app" class="pt-5">
    <v-layout class="pt-12">
      <v-flex md1>
        <v-layout column>
          <v-row class="pb-2">
            <v-card flat>
              <v-btn x-small>
              <v-icon>mdi-home</v-icon>
              </v-btn>
            </v-card>
          </v-row>
          <v-row>
            <v-card flat>
              <v-btn x-small>
                <v-icon>mdi-plus</v-icon>
              </v-btn>
            </v-card>
          </v-row>
        </v-layout>
      </v-flex>
      <v-flex md5>
        <v-card
          class="mx-auto"
          max-width="300"
          tile
        >
          <v-list shaped>
            <v-subheader>REPORTS</v-subheader>
            <v-list-item-group v-model="item" color="primary">
              <v-list-item
                v-for="(item, i) in items"
                :key="i"
              >
                <v-list-item-icon>
                  <v-icon v-text="item.icon"></v-icon>
                </v-list-item-icon>
                <v-list-item-content>
                  <v-list-item-title v-text="item.text"></v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list-item-group>
          </v-list>
        </v-card>
      </v-flex>
      <v-flex md6>
        <v-container  id="scroll-target"
                      style="max-height: 1000px"
                      class="overflow-y-auto">
          <v-row
            v-scroll:#scroll-target="onScroll"
            align="center"
            justify="center"
            style="height: 1000px"
          >
            <v-expansion-panels popout>
            <v-container v-for="n in 10"
                         :key="n">

                <v-sheet
                  class="mx-auto"
                  elevation="6"
                  max-width="1000"
                >
                  <v-slide-group
                    v-model="model"
                    class="pa-4"
                    :prev-icon="prevIcon ? 'mdi-minus' : undefined"
                    :next-icon="nextIcon ? 'mdi-plus' : undefined"
                    :multiple="multiple"
                    :mandatory="mandatory"
                    :show-arrows="showArrows"
                    :center-active="centerActive"
                  >
                    <v-slide-item
                      v-for="n in 15"
                      :key="n"
                      v-slot:default="{ active, toggle }"
                    >
                      <v-card
                        :color="active ? 'primary' : 'grey lighten-1'"
                        class="ma-4"
                        height="100"
                        width="100"
                        @click="toggle"
                      >
                        <v-row
                          class="fill-height"
                          align="center"
                          justify="center"
                        >
                          <v-expansion-panel>
                            <v-expansion-panel-header>Item</v-expansion-panel-header>
                            <v-expansion-panel-content>Test</v-expansion-panel-content>
                          </v-expansion-panel>
                          <v-scale-transition>
                            <v-icon
                              v-if="active"
                              color="white"
                              size="48"
                              v-text="'mdi-close-circle-outline'"
                            ></v-icon>
                          </v-scale-transition>
                        </v-row>
                      </v-card>
                    </v-slide-item>
                  </v-slide-group>
                </v-sheet>
            </v-container>
            </v-expansion-panels>
          </v-row>
        </v-container>
      </v-flex>
      <v-flex md6>
        <v-card>
          <v-card-text>
            <p>Test</p>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
    import TheNavBar from "../components/TheNavBar";
    export default {
        components: {TheNavBar},
        data: () => ({
            model: null,
            multiple: false,
            mandatory: false,
            showArrows: true,
            prevIcon: false,
            nextIcon: false,
            centerActive: false,
            offsetTop: 0,
            item: 1,
            items: [
                { text: 'Real-Time', icon: 'mdi-clock' },
                { text: 'Audience', icon: 'mdi-account' },
                { text: 'Conversions', icon: 'mdi-flag' },
            ],
        }),
        methods: {
            onScroll (e) {
                this.offsetTop = e.target.scrollTop
            },
        },
    }
</script>

