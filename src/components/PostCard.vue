<template>
  <div class="post-card content-box" :class="{'post-card--has-poster' : post.poster}">
    <div class="post-card__header">
      <g-image alt="Cover image" v-if="post.cover_image" class="post-card__image" :src="post.cover_image" />
    </div>
    <div class="post-card__content">
      <h2 class="post-card__title" v-html="post.title" />
      <p class="post-card__description" v-html="post.description" />

      <div>
        <a href="https://gumroad.com/l/zwIVA" target=“_blank” class="button primary button--large">
        Learn more ↘ ▶️ 👾 <img class="emojidex-emoji" src="https://cdn.emojidex.com/emoji/seal/ハート(虹).png" emoji-code="ハート(虹)" emoji-moji="❤‍🧡‍💛‍💚‍💙‍💜" alt="ハート(虹)" />
        </a>
      <br>
      <br>
        <a href="https://gumroad.com/l/zwIVA" target=“_blank” class="button primary button--large"> 
         Buy Now | Blog-in-a-Box  
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-arrow-right"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg></a> 
        <br>
        <br>
        <a class=“gumroad-button” href=“https://gumroad.com/l/zwIVA” target=“_blank”>Blog in a Box </a>
      </div>

      

      <!--  <a class=“gumroad-button” href=“https://gumroad.com/l/zwIVA” target=“_blank”>Blog in a Box </a> 

      <PostMeta class="post-card__meta" :post="post" /> -->
      <PostTags class="post-card__tags" :post="post" /> 

      <g-link class="post-card__link" :to="post.path">Link</g-link>

    </div>
  </div>
</template>

<script>
import PostMeta from '~/components/PostMeta'
import PostTags from '~/components/PostTags'

export default {
  components: {
    PostMeta,
    PostTags,
  },
  props: ['post'],
}
</script>

<style lang="scss">
.post-card {
  margin-bottom: var(--space);
  position: relative;

  &__header {
    margin-left: calc(var(--space) * -1);
    margin-right: calc(var(--space) * -1);
    margin-bottom: calc(var(--space) / 2);
    margin-top: calc(var(--space) * -1);
    overflow: hidden;
    border-radius: var(--radius) var(--radius) 0 0;

    &:empty {
      display: none;
    }
  }

  &__image {
    min-width: 100%;
  }

  &__title {
    margin-top: 0;
  }

  &:hover {
    transform: translateY(-5px);
    box-shadow: 1px 10px 30px 0 rgba(0,0,0,.1);
  }

  &__tags {
    z-index: 1;
    position: relative;
  }

  &__link {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    opacity: 0.0;
    overflow: hidden;
    text-indent: -9999px;
    z-index: 0;
  }

}
</style>
