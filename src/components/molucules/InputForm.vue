<template>
  <div :class="$style.inputForm">
    <form @submit.prevent>
      <input-text v-model="value" :searchText="value"></input-text>
      <primary-button label="追加" :iconSrc="imgSrc" @click="addTodo" :disabled="!value"/>
    </form>
  </div>
</template>

<script>
import InputText from '../atoms/InputText.vue';
import PrimaryButton from '../atoms/PrimaryButton.vue';

export default {
  components: {
    PrimaryButton,
    InputText
  },
  data() {
    return{
      imgSrc: "",
      value :'',
    }
  },
  props: {
    todo: {
      type: Object,
      required: true
    }
  },
  methods: {
    addTodo() {
      this.$emit('add', this.value);
      this.value = '';
    }
  }
}
</script>

<style module>
.inputForm {
  display: flex;
  justify-content: center; /* 水平方向の中央揃え */
  align-items: center;     /* 垂直方向の中央揃え */
  gap: 32px; /* input-text と primary-button の間のスペース */
  padding: 8px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  background-color: #f9f9f9;
  transition: background-color 0.3s;
}

.inputForm:hover {
  background-color: #f5f5f5;
}
</style>