<template>
  <v-container fluid class="pa-0 ma-0">
    <v-parallax src="/images/bg-home.png">
      <v-container>
        <v-row align="center" justify="start">
          <v-col cols="6">
            <div class="txt-header">Need someone to cook for you?</div>
            <div class="txt-header">Want to learn the secret cusinies?</div>
            <v-card class="pa-5 mt-5">
              <div class="mb-3 search-bar-header">Enter your postcode to find local Chefs</div>
              <div class="d-flex align-center">
                <v-text-field
                  v-model="first"
                  class="pr-5"
                  placeholder="e.g. EC4R 3TE"
                  background-color="#F7F7F7"
                  hide-details
                  solo
                  flat
                ></v-text-field>
                <v-btn color="primary" href="#">Search</v-btn>
              </div>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-parallax>
    <v-container>
      <div v-for="(item, i) in menuCategories" :key="i">
        <div class="d-flex justify-space-between">
          <h1 :class="'header-' + item.class">{{ item.title }}</h1>
          <v-btn color="primary" href="#">View More</v-btn>
        </div>
        <v-row>
          <v-col v-for="j in 3" :key="j">
            <MenuItemCard />
          </v-col>
        </v-row>
      </div>
    </v-container>
  </v-container>
</template>

<script>
import MenuItemCard from '~/components/cards/MenuItemCard.vue';

export default {
  components: {
    MenuItemCard,
    // VuetifyLogo,
  },
  data() {
    return {
      menuCategories: [
        { class: 'breakfast', title: 'Breakfast Menu' },
        { class: 'lunch', title: 'Lunch Menu' },
        { class: 'dinner', title: 'Dinner Menu' },
        { class: 'brunch', title: 'Brunch Menu' },
      ],
    };
  },
};
</script>
