<script setup>
import { ref, onMounted } from 'vue'

// Create a ref to hold the spinner element
const spinnerElement = ref(null)

onMounted(() => {
  // Access the spinner element using the ref value
  if (spinnerElement.value) {
    // spinnerElement.value.classList.remove('show')
  }
})
</script>

<template>
  <!-- Spinner Start -->
  <div
    ref="spinnerElement"
    class="show bg-white position-fixed translate-middle w-100 vh-100 top-50 start-50 d-flex align-items-center justify-content-center"
  >
    <div class="spinner-border text-primary" style="width: 3rem; height: 3rem" role="status">
      <span class="sr-only">Loading...</span>
    </div>
  </div>
  <!-- Spinner End -->
</template>

<style scoped>
/*** Spinner ***/
#spinner {
  opacity: 0;
  visibility: hidden;
  transition:
    opacity 0.5s ease-out,
    visibility 0s linear 0.5s;
  z-index: 99999;
}

#spinner.show {
  transition:
    opacity 0.5s ease-out,
    visibility 0s linear 0s;
  visibility: visible;
  opacity: 1;
}

.back-to-top {
  position: fixed;
  display: none;
  right: 45px;
  bottom: 45px;
  z-index: 99;
}

.my-6 {
  margin-top: 6rem;
  margin-bottom: 6rem;
}

.py-6 {
  padding-top: 6rem;
  padding-bottom: 6rem;
}
</style>
