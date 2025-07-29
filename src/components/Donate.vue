<template>
  <div class="donate-button-container">
    <button class="donate-button">Donate</button>
  </div>
</template>

<style scoped>
.donate-button-container {
  position: fixed;
  z-index: 20;
  width: 100%;
  padding: 0.75rem; 
  top: 1.25rem; 
  display: flex;
  justify-content: flex-end;
}

.donate-button {
  border: 4px solid #000;
  padding: 0.25rem 0.75rem;
  background-color: #fff;
  font-weight: bold;
  cursor: pointer;
  transition: all 0.3s ease;
}


@media (min-width: 768px) {
  .donate-button {
    padding: 0.5rem 1.5rem; 
    font-size: 1.125rem; 
  }
}
</style>