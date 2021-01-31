<template>
  <v-app id="inspire">


    <v-app-bar app dark>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-avatar
      color="warning lighten-2"
      size="39"
      class="ma-5"
      >
      <img src="../public/img/ic.png">
      </v-avatar>
      

      <v-toolbar-title class="teal--text">Trident Music</v-toolbar-title>
      <v-spacer></v-spacer>
       
    </v-app-bar>

    <v-navigation-drawer
      v-model="drawer"
      fixed
      temporary
      dark
    >
            <v-list-item>
        <v-list-item-content >
          <v-list-item-title class="title">
            Trident Music
                  <v-avatar
  color="warning lighten-2"
  size="9"
>
<img src="../public/img/ic.png">
</v-avatar>
          </v-list-item-title>
          <v-list-item-subtitle>
            @namowmita
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main class="black">
      <v-container>
        <v-row>
          <template v-for="cat in cats">
            <v-col
              :key="cat.id"
              class="ma-5"
              cols="12"
              
            >
              <strong class="teal--text" > {{ cat.title }}</strong>
              <v-divider class="teal"></v-divider>
            </v-col>

            <v-col
              v-for="j in 6"
              :key="`${cat.id}${j}`"
              cols="6"
              md="2"
            >
             
              <v-sheet height="100"   class="ma-4" width="150px">
                <v-card
                dark
                height="60"
                class="mb-10"
                
              >
              <div v-if="j===1">
                              <v-img
                height="100px"
                src="../public/img/1.jpg"
              >
              </v-img>
              </div>
              <div v-if="j===2">
                <v-img
                height="100px"
                src="../public/img/2.jpg"
              >
              </v-img>
              </div>
              <div v-if="j===3">
                 <v-img
                height="100px"
                src="../public/img/3.jpg"
              >
              </v-img>
              </div>
                <div v-if="j===4">
                  <v-img
                height="100px"
                src="../public/img/4.jpg"
              >
              </v-img>
              </div>
               
              <div v-if="j===5">
                  <v-img
                height="100px"
                src="../public/img/5.jpg"
              >
              </v-img>
              </div>
               
              <div v-if="j===6">
                  <v-img
                height="100px"
                src="../public/img/6.jpg"
              >
              </v-img>
              </div>

              <!-- <img :src="require('../public/img/2.jpg')" alt="" height="100px"> -->

              <v-card-subtitle class="pb-0">
                Number 10
              </v-card-subtitle>

              <v-card-text class="white--text">
                <div>Whitehaven Beach</div>


              </v-card-text>


            </v-card>
              </v-sheet>
             
            </v-col>
          </template>
        </v-row>

    <template>

      
     <v-bottom-navigation dark       
      
      height="100"
      fixed=true
      floating=true
      
      
      >
          <v-card tile  width="100%">
        <v-progress-linear
          :value="25"
          class="ma-2"
          height="5"

          color="purple"

        ></v-progress-linear>

        <v-list>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>The Walker</v-list-item-title>
              <v-list-item-subtitle>Fitz & The Trantrums</v-list-item-subtitle>
            </v-list-item-content>

            <v-spacer></v-spacer>

            <v-list-item-icon>
              <v-btn icon>
                <v-icon>mdi-rewind</v-icon>
              </v-btn>
            </v-list-item-icon>

            <v-list-item-icon :class="{ 'mx-50': $vuetify.breakpoint.mdAndUp }">
              <v-btn icon>
                <v-icon>mdi-pause</v-icon>
              </v-btn>
            </v-list-item-icon>

            <v-list-item-icon
              class="ml-0"
              :class="{ 'mr-0': $vuetify.breakpoint.mdAndUp }"
            >
              <v-btn icon>
                <v-icon>mdi-fast-forward</v-icon>
              </v-btn>
            </v-list-item-icon>
          </v-list-item>
        </v-list>
      </v-card>

  </v-bottom-navigation>
</template>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
  export default {
       data () {

      return {
        pa:"../public/img/1.jpg",
        cats:[
          {
            id:1,
            title:'Recomandations',
            src:'../public/img/2.jpg',

          },
          {
            id:2,
            title:'Continue listening',
            src:'../public/img/2.jpg',
          },
          {
            id:3,
            title:'Your list',
            src:'../public/img/2.jpg',
          },
          {
            id:4,
            title:'Your list',
            srci:'../public/img/4.jpg',
          }

        ],
            drawer: null,
        items: [
          { title: 'Home', icon: 'mdi-home' },
          { title: 'Search', icon: 'mdi-magnify' },
          { title: 'Libraries', icon: 'mdi-music-box' },
        ],
        right: null,
      }
    },
    methods: {
      getImgUrl(pic) {
        return require(pic)
      }
    },
        myFunction: function () {		
     return  Math.random()*100; //multiply to generate random number between 0, 100
    }  
  }
</script>
