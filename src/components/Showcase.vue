<template>
  <aside class="showcase" aria-hidden="true">
    <div class="phone">
      <div class="screen">
        <img class="showcase-img" src="../assets/demo.jpg" alt="showcase" />
      </div>
    </div>
  </aside>
</template>

<style scoped>
.showcase {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
}

.phone {
  width: 320px;
  height: 560px;
  border-radius: 36px;
  background: #fff;
  border: 1px solid var(--border);
  box-shadow: var(--shadow);
  display: flex;
  align-items: center;
  justify-content: center;
}

.screen {
  width: 300px;
  height: 520px;
  border-radius: 28px;
  overflow: hidden;
  position: relative;
  background: linear-gradient(180deg, #f7f7f7, #ededed);
}

.screen .showcase-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
</style>
