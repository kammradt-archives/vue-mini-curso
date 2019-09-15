<template>
  <v-app>
    <v-content>
      <v-container>
        
        <v-row>
          <v-col sm="12">
            <v-card class="pa-2">
              <v-card-title
                class="justify-center display-1 font-weight-light"
                v-text="'Meus depoimentos'"
              />
              <v-card-text>
                <v-text-field
                  counter="200"
                  label="Deixe seu recadinho"
                  v-model="novoDepoimento.texto"
                />
              </v-card-text>

              <v-row no-gutters>

                <v-col sm="12" md="4" align="center">
                  <v-rating
                    v-model="novoDepoimento.emoji"
                    size="35"
                    color="amber"
                    background-color="secondary"
                    empty-icon="mdi-thumb-up-outline"
                    full-icon="mdi-thumb-up"
                    hover
                  />
                </v-col>

                <v-col sm="12" md="4" align="center">
                  <v-rating
                    v-model="novoDepoimento.heart"
                    size="35"
                    color="red"
                    background-color="secondary"
                    empty-icon="mdi-heart-outline"
                    full-icon="mdi-heart"
                    hover
                  />
                </v-col>

                <v-col sm="12" md="4" align="center">
                  <v-rating
                    v-model="novoDepoimento.book"
                    size="35"
                    color="blue"
                    background-color="secondary"
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
                  class="primary"
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
        heart: 0,
        book: 0
      },
      depoimentos: []
    };
  },
  methods: {
    adicionarDepoimento() {
      if (this.novoDepoimento.texto && this.novoDepoimento.texto.length <= 200) {
        this.depoimentos.push(this.novoDepoimento);
        this.novoDepoimento = {};
      }
    }
  }
};
</script>
