<template>
  <div class="home">
    <h1>Welcome!</h1>
    <p>This is a Vue 3 + Vite application.</p>
    <div class="demo">
      <button @click="handleClick">Click Me</button>
      <p v-if="result">Result: {{ result }}</p>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'Home',
  setup() {
    const result = ref(null)

    const demoSum = (a, b) => {
      return Number(a) + Number(b)
    }

    const handleClick = () => {
      result.value = demoSum(1, 3)
    }

    return {
      result,
      handleClick
    }
  }
}
</script>

<style scoped>
.home {
  text-align: center;
  padding: 40px 20px;
}

h1 {
  color: #42b983;
  margin-bottom: 20px;
}

p {
  font-size: 18px;
  margin-bottom: 20px;
}

.demo {
  margin-top: 30px;
}

button {
  background-color: #42b983;
  color: white;
  border: none;
  padding: 12px 24px;
  font-size: 16px;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #35a372;
}
</style>
