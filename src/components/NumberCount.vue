<script setup>
import { ref, onMounted } from 'vue';

const props = defineProps({
  value: { type: Number, required: true },     // valeur finale
  duration: { type: Number, default: 1500 },   // durée en ms
  start: { type: Number, default: 0 },         // valeur de départ
  format: { type: Boolean, default: true }     // formatage avec séparateurs
});

const display = ref(props.start);
const animated = ref(false); // évite de rejouer l'animation

function easeOutCubic(t) {
  return 1 - Math.pow(1 - t, 3);
}

function animate() {
  const startTime = performance.now();
  const from = props.start;
  const to = props.value;

  function tick(now) {
    const elapsed = now - startTime;
    const progress = Math.min(elapsed / props.duration, 1);
    const eased = easeOutCubic(progress);
    const current = Math.round(from + (to - from) * eased);
    display.value = props.format ? current.toLocaleString() : current;

    if (progress < 1) {
      requestAnimationFrame(tick);
    }
  }
  requestAnimationFrame(tick);
}

onMounted(() => {
  const observer = new IntersectionObserver((entries, obs) => {
    if (entries[0].isIntersecting && !animated.value) {
      animate();
      animated.value = true;
      obs.unobserve(entries[0].target); // stoppe l'observation
    }
  }, { threshold: 0.3 }); // déclenche quand 30% visible

  observer.observe(document.querySelector('.count-wrapper'));
});
</script>

<template>
  <span class="count-wrapper">
    {{ display }}
  </span>
</template>