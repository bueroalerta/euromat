<template>
  <section class="intro">
    <div class="intro-content">
      <h1>{{ $t('intro.headline') }}</h1>

      <p
        v-for="(txt, index) of $t('intro.content')"
        :class="{ 'small': index === $t('intro.content').length -1 }">
        {{ txt }}
      </p>

      <router-link class="btn" :to="{ path: thesesPath }">
        {{ $t('intro.button') }}
        <feather-check-circle />
      </router-link>
    </div>
  </section>
</template>

<script>
  export default {
    name: 'Intro',

    computed: {
      thesesPath () {
        return this.$i18n.locale === 'de'
          ? '/thesen'
          : '/theses'
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import "~styles/layout";

  h1,
  p {
    margin-bottom: $base-gap;
  }

  p.small {
    font-size: $font-size-small;
  }

  .intro {
    position: relative;
  }

  .intro-content {
    position: relative;
    z-index: 1;
  }
</style>
