<template>
  <form class="form" @submit.prevent="handleSubmit" novalidate>
    <input
      v-model="user"
      type="text"
      placeholder="電話、使用者名稱或電子郵件"
      autocomplete="username"
      required
    />
    <div class="pw-row">
      <input
        v-model="password"
        :type="showPassword ? 'text' : 'password'"
        placeholder="密碼"
        autocomplete="current-password"
        required
      />
      <button type="button" aria-label="顯示密碼" @click="togglePassword">
        {{ showPassword ? "隱藏" : "顯示" }}
      </button>
    </div>
    <button class="btn primary" type="submit" :disabled="!isFormValid">
      {{ isLoading ? "登入中…" : "登入" }}
    </button>
    <div class="or-row"><span>或</span></div>
    <button type="button" class="btn fb" @click="loginWithFacebook">
      <svg class="fb-ico" viewBox="0 0 24 24" aria-hidden="true">
        <path
          fill="currentColor"
          d="M22 12a10 10 0 1 0-11.5 9.9v-7h-2.2v-2.9h2.2V9.1c0-2.2 1.3-3.4 3.3-3.4.95 0 1.95.17 1.95.17v2.1h-1.07c-1.06 0-1.39.66-1.39 1.33v1.6h2.36l-.38 2.9h-1.98v7A10 10 0 0 0 22 12z"
        ></path>
      </svg>
      以 Facebook 登入
    </button>
    <a class="forgot" href="#">忘記密碼？</a>
  </form>
</template>

<script setup>
import { ref, computed } from "vue";

const user = ref("");
const password = ref("");
const showPassword = ref(false);
const isLoading = ref(false);

const isFormValid = computed(() => user.value.trim() && password.value.trim());

const togglePassword = () => {
  showPassword.value = !showPassword.value;
};

const handleSubmit = async () => {
  if (!isFormValid.value) return;

  isLoading.value = true;
  try {
    await new Promise((resolve) => setTimeout(resolve, 900));
    alert("登入成功（範例）");
  } finally {
    isLoading.value = false;
  }
};

const loginWithFacebook = () => {
  alert("Facebook 登入（範例）");
};
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

input[type="text"],
input[type="password"] {
  padding: 10px;
  border: 1px solid var(--border);
  border-radius: var(--radius);
  font-size: 13px;
  background: var(--bg);
  color: #111;
}

input[type="text"]:focus,
input[type="password"]:focus {
  outline: none;
  border-color: var(--primary);
}

.pw-row {
  display: flex;
  gap: 8px;
  align-items: stretch;
}

.pw-row input {
  flex: 1;
}

.pw-row button {
  padding: 0 10px;
  border: 1px solid var(--border);
  border-radius: var(--radius);
  background: var(--bg);
  color: var(--primary);
  font-size: 13px;
  font-weight: 600;
  cursor: pointer;
  transition: background-color 0.2s;
}

.pw-row button:hover {
  background: #f5f5f5;
}

.btn {
  padding: 8px;
  border: none;
  border-radius: var(--radius);
  font-size: 14px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s;
}

.btn.primary {
  background: var(--primary);
  color: #fff;
}

.btn.primary:disabled {
  background: #b3d9f2;
  cursor: not-allowed;
}

.btn.primary:not(:disabled):hover {
  background: #0a8cdb;
}

.btn.fb {
  background: var(--fb);
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}

.btn.fb:hover {
  background: #165ac3;
}

.fb-ico {
  width: 16px;
  height: 16px;
}

.or-row {
  display: flex;
  align-items: center;
  margin: 4px 0;
  color: var(--muted);
  font-size: 13px;
}

.or-row::before,
.or-row::after {
  content: "";
  flex: 1;
  height: 1px;
  background: var(--border);
}

.or-row span {
  padding: 0 16px;
}

.forgot {
  align-self: center;
  font-size: 12px;
  color: var(--primary);
  text-decoration: none;
  margin-top: 4px;
}

.forgot:hover {
  text-decoration: underline;
}
</style>
