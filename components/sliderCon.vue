<template>
  <div class="slide">
    <transition name="slide-fade">
      <slot />
    </transition>
  </div>
</template>

<style>
.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: opacity 0.7s ease-in-out;
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  opacity: 0;
}

.slide-fade-enter-to,
.slide-fade-leave-from {
  opacity: 1;
}
</style>
