<template>
  <v-app>
    <v-app-bar id="header" fixed app color="#D8D6CB">
      <v-container class="d-flex justify-space-between align-center">
        <div class="header-logo"></div>
        <div class="menu-items d-flex align-center">
          <div>Explore</div>
          <div>Meal Menu <v-icon> mdi-chevron-down </v-icon></div>
          <div>Find a Chef</div>
          <div>Bookings</div>
          <div>
            <v-avatar size="44">
              <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John" />
            </v-avatar>
            <v-icon> mdi-chevron-down </v-icon>
          </div>
        </div>
      </v-container>
    </v-app-bar>
    <v-main>
      <nuxt />
    </v-main>
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

  &:not(.v-btn--flat) {
    padding: 0 25px !important;
  }

  &.postal-search {
    padding: 21px 66px !important;
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

#header {
  height: 108px !important;
  .v-toolbar__content {
    height: 100% !important;
  }
  .header-logo {
    background-image: url('/images/icons/header-logo.svg');
    width: 88px;
    height: 66px;
  }

  .menu-items {
    & > div {
      margin-left: 40px;
      // font-family: 'Cera Pro';
      font-style: normal;
      font-weight: 500;
      font-size: 14px;
      line-height: 18px;
      text-align: center;

      color: #000000;
    }
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
  height: 70px;
  font-family: 'Cormorant';
  font-style: normal;
  font-weight: 600;
  font-size: 32px;
  line-height: 70px;
  padding-left: 80px;
  background-position: center left;

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
