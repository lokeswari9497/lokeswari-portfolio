<template>
  <v-footer class="pa-6" height="auto">
    <v-container>
      <v-row align="center" justify="space-between" no-gutters>
        <!-- Name or Logo -->
        <v-col cols="12" md="4" class="text-center text-md-start mb-4 mb-md-0">
          <strong class="text-h6">Lokeswari</strong>
        </v-col>

        <!-- Social or Nav Links -->
        <v-col cols="12" md="4" class="text-center mb-4 mb-md-0">
          <v-btn
            icon
            href="https://www.linkedin.com/in/lokeswari-m/"
            target="_blank"
            class="mx-2"
            variant="plain"
          >
            <v-icon>mdi-linkedin</v-icon>
          </v-btn>
          <v-btn
            icon
            href="https://github.com/lokeswari9497"
            target="_blank"
            class="mx-2"
            variant="plain"
          >
            <v-icon>mdi-github</v-icon>
          </v-btn>
        </v-col>

        <!-- Copyright -->
        <v-col cols="12" md="4" class="text-center text-md-end">
          <small>&copy; All rights reserved.</small>
        </v-col>
      </v-row>
    </v-container>
  </v-footer>
</template>
<style scoped>
.v-footer {
    background: #BDBDBD;
    color: #000000;
}
</style>