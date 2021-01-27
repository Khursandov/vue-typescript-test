<template>
    <div class="input">
        <i class="input--icon" :class="icon + (active ? ' text-primary' : '') "></i>
        <input :placeholder="label" @focus="active = true" @blur="active = false" :type="type" v-model="value" class="input--field text-left" @input="onChange">
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component

export default class CustomInput extends Vue {
  // Label of input
  @Prop() label!: string;

  // Type of input, default value is text
  @Prop({default: 'text'}) type!: string;

  // Image source for icon
  @Prop() icon!: string;
  
  value = ''
  active = false

  onChange() {
    this.$emit('onInput', this.value);
  }
}


</script>

<style lang="scss">
.input {
  width: 100%; 
  margin-bottom: 18px;
  position: relative;

  &--icon {
    position: absolute;
    width: 18px;
    height: 18px;
    bottom: 13px;
    color: #DEDEDE;
  }

  &--field {
    padding: 10px 29px; 
    font-size: 18px;
    line-height: 22px;
    border: none;
    font-family: Inter;
    color: #595959;
    border-bottom: solid 2px #DEDEDE;
    transition: all .3s;

    &:focus {
      outline: none;
      border-bottom: solid 2px #0075FF;
    }

    &:before {
      content: "";
      background: #0075FF;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      position: absolute;
    }
  }
}

</style>