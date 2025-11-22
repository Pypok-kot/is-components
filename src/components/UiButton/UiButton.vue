<template>
  <button :class="$style.button" :data-layout="props.layout" :disabled="props.isDisabled" :type="props.type">
    <slot></slot>
  </button>
</template>

<script setup lang="ts">
interface IProps {
  layout?: 'primary' | 'secondary';
  type?: 'submit' | 'button';
  isDisabled?: boolean;
}

const props = withDefaults(defineProps<IProps>(), {
  layout: 'primary',
  type: 'button',
});
</script>

<style module lang="scss">
.button {
  position: relative;
  display: inline-flex;
  gap: 8px;
  align-items: center;
  justify-content: center;
  height: 40px;
  padding: 16px 32px;
  font-size: 1rem;
  line-height: 1.5;
  color: #000000;
  background: #ffd904;
  border: 2px solid #000000;
  border-radius: 16px;
  cursor: pointer;
  transition: all 0.3s ease;

  &:hover {
    background: #000000;
    color: #ff7b00;
    border-color: #ff7b00;
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(255, 123, 0, 0.3);
  }

  &[data-layout='secondary'] {
    color: #000000;
    background-color: transparent;
    border-color: #000000;
  } 
}
  </style>
