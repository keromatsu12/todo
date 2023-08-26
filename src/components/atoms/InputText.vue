<template>
  <input :class="$style.input" 
          placeholder="タスクを入力" 
          v-model="innerSearchText"/>
</template>

<script>
export default {
  props: {
    searchText: String
  },
  computed: {
    innerSearchText: {
      get () {
        return this.$props.searchText
      }
    }}
}
</script>

<style module>
.input {
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  transition: padding 0.3s, font-size 0.3s;  /* 追加: スムーズな遷移 */
}
</style>
