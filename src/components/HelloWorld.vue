<script setup lang="ts">
import { useCounter } from '../composables/useCounter'

defineProps<{ msg: string }>()

// Using the composable
const { count, doubleCount, increment, decrement, reset } = useCounter(0)
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <div class="counter-display">
      <p class="count-text">Count: <span class="count-value">{{ count }}</span></p>
      <p class="count-text">Double Count: <span class="count-value">{{ doubleCount }}</span></p>
    </div>
    
    <div class="button-group">
      <button type="button" @click="decrement" class="btn-decrement">-</button>
      <button type="button" @click="increment" class="btn-increment">+</button>
      <button type="button" @click="reset" class="btn-reset">Reset</button>
    </div>
    
    <p class="description">
      This counter uses a composable with Vue 3 Composition API
    </p>
  </div>

  <p class="read-the-docs">Built with Vue 3, TypeScript, Vite, and SCSS</p>
</template>

<style scoped lang="scss">
@use 'sass:color';

$counter-color: #42b883;
$increment-color: #4caf50;
$decrement-color: #f44336;
$reset-color: #ff9800;

.card {
  padding: 2em;
  
  .counter-display {
    margin-bottom: 1.5em;
    
    .count-text {
      font-size: 1.2em;
      margin: 0.5em 0;
      
      .count-value {
        color: $counter-color;
        font-weight: bold;
        font-size: 1.3em;
      }
    }
  }
  
  .button-group {
    display: flex;
    gap: 1em;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 1em;
    
    button {
      min-width: 80px;
      
      &.btn-increment {
        background-color: $increment-color;
        
        &:hover {
          background-color: color.adjust($increment-color, $lightness: -10%);
          border-color: $increment-color;
        }
      }
      
      &.btn-decrement {
        background-color: $decrement-color;
        
        &:hover {
          background-color: color.adjust($decrement-color, $lightness: -10%);
          border-color: $decrement-color;
        }
      }
      
      &.btn-reset {
        background-color: $reset-color;
        
        &:hover {
          background-color: color.adjust($reset-color, $lightness: -10%);
          border-color: $reset-color;
        }
      }
    }
  }
  
  .description {
    font-size: 0.9em;
    color: #888;
    font-style: italic;
  }
}

.read-the-docs {
  color: #888;
  font-size: 0.9em;
}
</style>
