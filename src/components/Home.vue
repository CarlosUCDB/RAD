<template>
  <v-content>
    <v-container>
      <v-row>
        <v-col>
          <v-card>
            <v-img class="white--text align-end" height="200px" :src="images.topo"></v-img>
            <v-card-title>{{curso.titulo}}</v-card-title>
            <v-card-text>{{curso.subTitulo}}</v-card-text>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-col>
          <v-card>
            <v-card-title>Detalhes</v-card-title>
            <v-card-text>{{curso.detalhes}}</v-card-text>
          </v-card>
        </v-col>

        <v-col>
          <v-card>
            <v-card-title>Metodologia</v-card-title>
            <v-card-text>{{curso.metodologia}}</v-card-text>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-col>
          <v-card>
            <v-card-title>Tópicos</v-card-title>
            <v-card-text>
              <v-expansion-panels>
                <v-expansion-panel v-for="(item,i) in curso.topicos" :key="i">
                  <v-expansion-panel-header>{{item.titulo}}</v-expansion-panel-header>
                  <v-expansion-panel-content>{{item.sub}}</v-expansion-panel-content>
                </v-expansion-panel>
              </v-expansion-panels>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col>
          <v-card>
            <v-card-title>Estrutura</v-card-title>
            <v-container>
              <v-col>
                <v-card class="text-center pt-5 pb-5">
                   <img width="250" :src="images.imagens1" />
                </v-card>
              </v-col>
              <v-col>
                <v-card class="text-center pt-5 pb-5">
                   <img width="250" :src="images.imagens2" />
                </v-card>
              </v-col>
            </v-container>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-col>
          <v-card>
            <v-card-title>Próxima Turma</v-card-title>
            <v-card-text>
              <ul>
                <li>{{curso.turma.inicio}}</li>

                <li>{{curso.turma.dias}}</li>

                <li>{{curso.turma.cargaHoraria}}</li>
              </ul>
            </v-card-text>
          </v-card>
        </v-col>

        <v-col>
          <v-card>
            <v-card-title>Contato</v-card-title>
            <v-card-text>
              <v-container>
                <v-row>
                  <v-col>
                    <a
                      style="text-decoration: none;"
                      target="_blank"
                      href="http://bit.ly/whatsapp-ht2"
                    >
                      <v-icon>mdi-whatsapp</v-icon>
                      {{curso.contato.whatsApp}}
                    </a>

                    <ul>
                      <li>{{curso.contato.telefone}}</li>
                      <li>{{curso.contato.email}}</li>
                    </ul>
                  </v-col>
                </v-row>
              </v-container>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-col>
          <v-card>
            <v-card-title>Localização</v-card-title>
            <iframe
              width="100%"
              src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d119584.5497361193!2d-54.597575!3d-20.505522!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0xa6ffe06c33e2057c!2sHigh%20Tech%20Cursos!5e0!3m2!1spt-BR!2sbr!4v1582244418152!5m2!1spt-BR!2sbr"
              height="450"
              frameborder="0"
              style="border:0;"
              allowfullscreen
            ></iframe>
          </v-card>
        </v-col>
      </v-row>

      <v-row class="text-center blue">
        <v-col>
          <img
            width="10%"
            src="https://www.fabricadeprogramador.com.br/img/logo-ht-white.fe4318dd.svg"
          />
        </v-col>
      </v-row>

      <v-row class="text-center blue">
        <v-col class="white--text">©Copyright 2020 High Tech Cursos - All Rights Reserved - Legal</v-col>
      </v-row>
    </v-container>
  </v-content>
</template>

<script>
import json from '../data/kotlin.json'
export default {
  name: "Home",
  data() {
    return {
      curso: undefined,
      images: {
         topo: require("../assets/top2.png"),
         imagens1: require("../assets/img1.jpg"),
         imagens2: require("../assets/img2.jpg")
      }
    }
  },
  created(){
      this.curso = json

  },
}
</script>
