<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://i.pinimg.com/originals/fd/8d/d9/fd8dd97c28e06fbd8f3168266eb332d4.png"
          transition="scale-transition"
          width="40"
        />
          <v-menu
              v-model="value"
              :open-on-hover="openOnHover"
              :close-on-click="closeOnClick"
              :close-on-content-click="closeOnContentClick"
              :offset-x="offsetX"
              :offset-y="offsetY"
          >
              <template v-slot:activator="{ on, attrs }">
                  <v-btn
                      color="primary"
                      dark
                      v-bind="attrs"
                      v-on="on"
                  >
                      Футбольная статистика
                  </v-btn>
              </template>
              <v-list>
                  <v-list-item
                      v-for="(item, index) in items"
                      :key="index"
                      @click="testMethod"
                  >
                      <v-list-item-title>{{ item.title }}</v-list-item-title>
                  </v-list-item>
              </v-list>
          </v-menu>

      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://simbirsoft.timepad.ru/event/1649203/"
        target="_blank"
        text
      >
        <span class="mr-2">Simbirsoft</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <HelloWorld/>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    HelloWorld,
  },

  data: () => ({
      items: [
          { title: 'Лиги' },
          { title: 'Календарь лиги' },
          { title: 'Команды' },
          { title: 'Календарь команды' },
      ],
      value: false,
      closeOnClick: true,
      closeOnContentClick: true,
      offsetX: false,
      offsetY: true,
  }),
    methods: {
        testMethod: (value) => {
            alert(value);
        }
    }

};
</script>
