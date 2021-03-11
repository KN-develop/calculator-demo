<template>
  <v-container>
    <v-row class="text-center">

      <v-col
        class="mb-5"
        cols="12"
      >
        <v-row justify="center">
          <Calculator />
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import Calculator from "@/components/Calculator";
  export default {
    name: 'HelloWorld',

    components: {Calculator},
  }
</script>
