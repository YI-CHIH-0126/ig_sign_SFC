<template>
  <div class="card auth-card">
    <h1 class="logo"><span class="grad">Instagram</span></h1>
    <LoginForm />
  </div>
</template>

<script setup>
import LoginForm from "./LoginForm.vue";
</script>

<style scoped>
.card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 40px;
  width: 100%;
  max-width: 350px;
}

.logo {
  text-align: center;
  font-size: 32px;
  font-weight: 700;
  margin: 0 0 32px 0;
  line-height: 1.2;
}

.grad {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
</style>
