<template>
  <v-app>
    <v-content>
      <v-container>
        <v-row>
          <v-col cols="12" sm="12">
            <v-card class="pa-2">
              <v-card-title
                class="justify-center display-1 font-weight-light"
                v-text="'Meus depoimentos'"
              />
              <v-card-text>
                <v-text-field v-model="novoDepoimento.texto" label="Digite seu recadinho" />
              </v-card-text>

              <v-row no-gutters>
                <v-col cols="12" sm="12" md="4" align="center" justify="center">
                  <v-rating
                    v-model="novoDepoimento.emoji"
                    size="35"
                    color="amber lighten-2"
                    background-color="grey lighten-1"
                    empty-icon="mdi-thumb-up-outline"
                    full-icon="mdi-thumb-up"
                    hover
                  />
                </v-col>
                <v-col cols="12" sm="12" md="4" align="center" justify="center">
                  <v-rating
                    v-model="novoDepoimento.core"
                    size="35"
                    color="red"
                    background-color="grey lighten-1"
                    empty-icon="mdi-heart-outline"
                    full-icon="mdi-heart"
                    hover
                  />
                </v-col>
                <v-col cols="12" sm="12" md="4" align="center" justify="center">
                  <v-rating
                    v-model="novoDepoimento.livro"
                    size="35"
                    color="blue"
                    background-color="grey lighten-1"
                    empty-icon="mdi-book-outline"
                    full-icon="mdi-book"
                    hover
                  />
                </v-col>
              </v-row>

              <v-card-actions>
                <v-btn
                  @click="adicionarDepoimento"
                  block
                  dark
                  color="#d744b6"
                  v-text="'Adicionar depoimento'"
                />
              </v-card-actions>
            </v-card>
          </v-col>

          <v-col v-for="depoimento in depoimentos" :key="depoimento.texto" cols="12" sm="12">
            <Depoimento :depoimento="depoimento" />
          </v-col>
        </v-row>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import Depoimento from "@/components/Depoimento";

export default {
  name: "App",
  components: {
    Depoimento
  },
  data() {
    return {
      novoDepoimento: {
        texto: "",
        emoji: 0,
        core: 0,
        livro: 0
      },
      depoimentos: []
    };
  },
  methods: {
    adicionarDepoimento() {
      if (this.novoDepoimento.texto) {
        this.depoimentos.push(this.novoDepoimento);
        this.novoDepoimento = {};
      }
    }
  }
};
</script>
