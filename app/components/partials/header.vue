<template>
  <header class="flex items-center py-4 md:py-8">
    <div class="header__logo">
      <nuxt-link to="/">
        <img :src="logo" alt="Logo" />
      </nuxt-link>
    </div>

    <nav class="nav ml-auto">
      <ul class="flex flex-row items-center sm:mt-4 sm:pt-4 md:mt-0 md:pt-0 md:mr-4 lg:mr-8">
        <li>
          <nuxt-link to="/blog" class="block font-medium px-4 py-1 md:p-2 lg:px-4">
            Blog
          </nuxt-link>
        </li>

        <li
          v-for="(page, index) in pages"
          :key="index"
          class="block font-medium px-4 py-1 md:p-2 lg:px-4"
        >
          <nuxt-link :to="`/${page.slug}`">{{ page.title }}</nuxt-link>
        </li>
        <div style="width: 100%" id="c24pp-dsl-iframe"></div>
                <li class="block font-medium px-4 py-1 md:p-2 lg:px-4" ><a href="index-cc.credit.card.html">Kreditkarte</a></li>
                        <li class="block font-medium px-4 py-1 md:p-2 lg:px-4" ><a href="index-banc.acc.html">Girokonto</a></li>
        <li class="block font-medium px-4 py-1 md:p-2 lg:px-4" ><a href="index-dsl.html">DSL-Vergleich</a></li>
        <li class="block font-medium px-4 py-1 md:p-2 lg:px-4" ><a href="index-kfz.html">KFZ-Vergleich</a></li>
        <li class="block font-medium px-4 py-1 md:p-2 lg:px-4" ><a href="index-strom.html">Strom-Vergleich</a></li>
        <li class="block font-medium px-4 py-1 md:p-2 lg:px-4" ><a href="impressum.html">Impressum</a></li>
      </ul>
    </nav>
  </header>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

import LogRocket from 'logrocket';
LogRocket.init('cjlodg/tarif');

@Component
export default class Header extends Vue {
  get pages(): Page[] {
    return this.$store.state.pages;
  }

  logo = settings.logo;
}
</script>

<style lang="scss">
.nav {
  ul li > a {
    &.nuxt-link-active {
      color: $bluise;
      @apply font-bold;
    }
  }
}
</style>
