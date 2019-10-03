<template>
    <nav class="nav">
      <div class="theToolbar">
      <v-toolbar absolute
      >
        <v-toolbar-title>
          <v-avatar width="10">
            <v-img src="t.jpg"></v-img>
          </v-avatar>
        </v-toolbar-title>

        <v-divider
          hidden
          inset
          vertical
        ></v-divider>

        <v-toolbar-items class="hidden-sm-and-down subheading" >
          <v-card-text>
            HOME
          </v-card-text>
        </v-toolbar-items>
        <v-spacer></v-spacer>

        <v-toolbar-items class="hidden-sm-and-down">
          <v-card flat>
          <v-text-field
            label="Search..."
            append-icon="mdi-magnify"
          >
          </v-text-field></v-card>
          <v-card flat>
          <v-btn text>
            Sign Out
          </v-btn></v-card>
        </v-toolbar-items>
      </v-toolbar>
      </div>
    </nav>
</template>

<script>
    export default {
        name: "TheNavBar",
        data: {

        }
    }
</script>

<style scoped>

</style>
