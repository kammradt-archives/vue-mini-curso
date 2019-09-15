<template>
  <v-card class="pa-2">
    <v-card-title>{{ depoimento.texto }}</v-card-title>
    <v-card-actions>

      <v-row no-gutters>

        <v-col sm="12" md="4" align="center">
          <v-rating
            :value="depoimento.emoji"
            size="35"
            color="amber"
            background-color="secondary"
            empty-icon="mdi-thumb-up-outline"
            full-icon="mdi-thumb-up"
            readonly
          />
        </v-col>

        <v-col sm="12" md="4" align="center">
          <v-rating
            :value="depoimento.heart"
            size="35"
            color="red"
            background-color="secondary"
            empty-icon="mdi-heart-outline"
            full-icon="mdi-heart"
            readonly
          />
        </v-col>

        <v-col sm="12" md="4" align="center">
          <v-rating
            :value="depoimento.book"
            size="35"
            color="blue"
            background-color="secondary"
            empty-icon="mdi-book-outline"
            full-icon="mdi-book"
            readonly
          />
        </v-col>

      </v-row>
      
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  props: {
    depoimento: Object
  }
};
</script>

