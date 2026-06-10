<template>
  <div class="card signup-card">沒有帳號嗎？ <a href="#">註冊</a></div>
</template>

<style scoped>
.card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 20px;
  width: 100%;
  max-width: 350px;
  text-align: center;
  font-size: 14px;
  color: #111;
}

a {
  color: var(--primary);
  text-decoration: none;
  font-weight: 600;
}

a:hover {
  text-decoration: underline;
}
</style>
