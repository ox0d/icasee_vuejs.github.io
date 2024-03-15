<script setup>
import { ref, onMounted } from 'vue'

const initialValues = {
  heldConferences: ref(0),
  keynoteSpeakers: ref(0),
  speakers: ref(0),
  participants: ref(0),
  sponsors: ref(0)
}

const targetValues = {
  heldConferences: 6,
  keynoteSpeakers: 6,
  speakers: 63,
  participants: 115,
  sponsors: 3
}

const animateNumbers = () => {
  Object.keys(targetValues).forEach(function (key) {
    const interval = setInterval(function () {
      if (initialValues[key].value < targetValues[key]) {
        initialValues[key].value++
      } else {
        clearInterval(interval)
      }
    }, 15)
  })
}

onMounted(() => {
  animateNumbers()
})
</script>

<template>
  <!-- counter-section Start -->
  <div class="container-fluid bg-primary my-6 wow fadeInUp" data-wow-delay="0.1s">
    <div class="container-fluid">
      <div class="row justify-content-center pt-5 pb-2 text-center align-middle">
        <div class="col-6 col-sm-4 col-lg-2 pb-3">
          <div class="row pb-3">
            <i class="text-white fa fa-chart-line fa-3x"></i>
          </div>
          <div class="row">
            <div class="col">
              <h1 class="text-white">{{ initialValues.heldConferences }}</h1>
              <h6 class="text-white">Held Conferences</h6>
            </div>
          </div>
        </div>
        <div class="col-6 col-sm-4 col-lg-2 pb-3 text-center">
          <div class="row pb-3">
            <i class="text-white fa fa-microphone fa-3x"></i>
          </div>
          <div class="row">
            <div class="col">
              <h1 class="text-white">{{ initialValues.keynoteSpeakers }}</h1>
              <h6 class="text-white">Keynote Speakers</h6>
            </div>
          </div>
        </div>
        <div class="col-6 col-sm-4 col-lg-2 pb-3 text-center">
          <div class="row pb-3">
            <i class="text-white fa fa-chalkboard fa-3x"></i>
          </div>
          <div class="row">
            <div class="col">
              <h1 class="text-white">{{ initialValues.speakers }}</h1>
              <h6 class="text-white">Speakers</h6>
            </div>
          </div>
        </div>
        <div class="col-6 col-sm-4 col-lg-2 pb-3 text-center">
          <div class="row pb-3">
            <i class="text-white fa fa-toolbox fa-3x"></i>
          </div>
          <div class="row">
            <div class="col">
              <h1 class="text-white">{{ initialValues.participants }}</h1>
              <h6 class="text-white">Participants</h6>
            </div>
          </div>
        </div>
        <div class="col-6 col-sm-4 col-lg-2 pb-3 text-center">
          <div class="row pb-3">
            <i class="text-white fa fa-handshake fa-3x"></i>
          </div>
          <div class="row">
            <div class="col">
              <h1 class="text-white">{{ initialValues.sponsors }}</h1>
              <h6 class="text-white">Sponsors</h6>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- counter-section End -->
</template>
