<template>
  <v-app>

    <!-- Sizes your content based upon application components -->
    <v-content>
      <v-container fluid>
        <v-row>
          <v-col cols="12">
            <v-row
              class="d-flex flex-row justify-space-between"
              center
              center
            >
              <v-card>
                <v-row al>
                <v-img src="t.jpg" max-width="30" max-height="30"></v-img>
                <v-btn height="30" width="30">Home</v-btn>
                </v-row>
              </v-card>
              <v-card>
                  <v-btn height="30" width="30">Log In</v-btn>
                  <v-btn height="30" width="30">Sign Up</v-btn>
              </v-card>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </v-content>
    <v-footer
      dark
      padless
    >
      <v-card
        class="flex"
        flat
        tile
      >
        <v-card-actions class="grey darken-3 justify-center">
          {{ new Date().getFullYear() }} — <strong>connectome</strong>
        </v-card-actions>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
    export default {
        data () {
            return {
                alignmentsAvailable: [
                    'start',
                    'center',
                    'end',
                    'baseline',
                    'stretch',
                ],
                alignment: 'center',
                dense: false,
                justifyAvailable: [
                    'start',
                    'center',
                    'end',
                    'space-around',
                    'space-between',
                ],
                justify: 'center',
            }
        },
    }
</script>

