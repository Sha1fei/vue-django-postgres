<template>
		<div class='feed-articles__article'>
      <div class='feed-articles__article_gradient' ></div>
      <p v-for="paragraph, i in props.content" :key="i">{{paragraph}}</p>
    </div>
</template>

<script setup lang="ts">
  interface IProps {
    content: string[]
  }
  const props = defineProps<IProps>()
</script>

<style lang="scss">
@import '@app/app.scss';

.feed-articles{
  &__header{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }
  &__stars_liked{
    border: 1px $blue-color solid;
    border-radius: 5px;
    padding-left: 4px;
    padding-right: 4px;
    padding-bottom: 1px;
    color: $blue-color;
  }
  &__userinfo{
    display: flex;
    flex-direction: row;
    align-items: center;
 
    &-content{
      margin-left: 8px;
      display: flex;
      flex-direction: column;
      & h5{
        margin-bottom: 0;
      }
    }
  }
  &__article{
    max-height: 150px;
    overflow: hidden;
    position: relative;
  }
  &__pagination{
    display: flex;
    justify-content: center;
  }
  &__article_gradient{
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(transparent, white);
  }
  &__read-more{
    color: $blue-color !important;
  }
  &__article_text{
    text-indent: 20px
  }
  &__grade{
    cursor: pointer
  }
}
</style>