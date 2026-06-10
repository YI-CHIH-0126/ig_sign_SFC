<template>
  <div class="page">
    <Logo />
    <div class="stage">
      <Showcase />
      <section class="auth-area">
        <LoginCard />
        <SignupCard />
      </section>
    </div>
  </div>
</template>

<script setup>
import Logo from "./Logo.vue";
import Showcase from "./Showcase.vue";
import LoginCard from "./LoginCard.vue";
import SignupCard from "./SignupCard.vue";
</script>

<style scoped>
.page {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 40px;
}

.stage {
  display: flex;
  gap: 48px;
  align-items: center;
  max-width: 980px;
  width: 100%;
}

.auth-area {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 12px;
  align-items: center;
}
</style>
