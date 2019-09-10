<template>
  <v-card class="pa-2">
    <v-card-title>{{depoimento.texto}}</v-card-title>
    <v-card-actions>
      <v-row no-gutters>
        <v-col cols="12" sm="12" md="4" align="center" justify="center">
          <v-rating
            :value="depoimento.emoji"
            size="35"
            color="amber lighten-2"
            background-color="grey lighten-1"
            empty-icon="mdi-thumb-up-outline"
            full-icon="mdi-thumb-up"
            readonly
          />
        </v-col>
        <v-col cols="12" sm="12" md="4" align="center" justify="center">
          <v-rating
            :value="depoimento.core"
            size="35"
            color="red"
            background-color="grey lighten-1"
            empty-icon="mdi-heart-outline"
            full-icon="mdi-heart"
            readonly
          />
        </v-col>
        <v-col cols="12" sm="12" md="4" align="center" justify="center">
          <v-rating
            :value="depoimento.livro"
            size="35"
            color="blue"
            background-color="grey lighten-1"
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

