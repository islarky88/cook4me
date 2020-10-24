<template>
  <v-app dark>
    <!-- <v-navigation-drawer v-model="drawer" app>
      <v-list>
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to" router exact>
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer> -->
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-btn icon @click.stop="clipped = !clipped">
        <v-icon>mdi-application</v-icon>
      </v-btn>
      <v-btn icon @click.stop="fixed = !fixed">
        <v-icon>mdi-minus</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn icon @click.stop="rightDrawer = !rightDrawer">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <nuxt />
    </v-main>
    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light> mdi-repeat </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
    };
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Cormorant&family=Roboto&display=swap');
.v-main {
  background-color: #eeede8;
}

.v-btn {
  border-radius: 2px;
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 500;
  font-size: 12px !important;
  line-height: 12px;
  text-align: center;
  letter-spacing: 1px;
  text-transform: uppercase;
  color: #ffffff;
  height: 32px !important;

  &.postal-search {
    padding: 21px 50px !important;
    // font-family: 'Cera Pro';
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 18px;
    text-align: center;
    letter-spacing: 0.0357143em;
    text-transform: uppercase;
  }
}

.txt-header {
  font-family: 'Cormorant';
  font-style: normal;
  font-weight: bold;
  font-size: 40px;
  line-height: 48px;
}

h1 {
  font-family: 'Cormorant';
  font-style: normal;
  font-weight: 600;
  font-size: 32px;
  line-height: 39px;
  padding-left: 80px;

  &.header-breakfast {
    background-image: url('/images/icons/header/breakfast.svg');
  }
  &.header-lunch {
    background-image: url('/images/icons/header/lunch.svg');
  }
  &.header-dinner {
    background-image: url('/images/icons/header/dinner.svg');
  }
  &.header-brunch {
    background-image: url('/images/icons/header/brunch.svg');
  }
}

.search-bar-header {
  font-family: 'Cormorant';
  font-style: normal;
  font-weight: bold;
  font-size: 16px;
  line-height: 19px;
  color: #0c0c0c;
}

.card-title {
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 500;
  font-size: 20px;
  line-height: 23px;
}
.card-author {
  font-family: 'Roboto';
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 16px;
  color: rgba(0, 0, 0, 0.87);
}
</style>
