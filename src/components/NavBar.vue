<script setup>
import { ref, onMounted } from 'vue'

onMounted(() => {
  const logoImage = ref(document.getElementById('logoImage'))

  function updateImageSource() {
    if (window.matchMedia('(max-width: 991.98px)').matches) {
      // Change the image source for smaller screens
      logoImage.value.src = '/src/assets/img/icasee_logo_green.webp'
    } else {
      // Revert to the original image source for larger screens
      logoImage.value.src = '/src/assets/img/icasee_logo_white.webp'

      // Sticky Navbar
      window.addEventListener('scroll', () => {
        if (window.scrollY > 45) {
          document.querySelector('.navbar').classList.add('sticky-top', 'shadow-sm')
          logoImage.value.src = '/src/assets/img/icasee_logo_green.webp'
        } else {
          document.querySelector('.navbar').classList.remove('sticky-top', 'shadow-sm')
          if (window.matchMedia('(min-width: 991.99px)').matches) {
            logoImage.value.src = '/src/assets/img/icasee_logo_white.webp'
          }
        }
      })
    }
  }

  // Call the function on page load
  updateImageSource()

  // Attach the function to the resize event
  window.addEventListener('resize', updateImageSource)
})
</script>

<template>
  <!-- Navbar Start -->
  <nav class="navbar navbar-expand-lg navbar-light px-4 px-lg-5 py-3 py-lg-0">
    <a href="index.html" class="navbar-brand p-0">
      <!-- <h1 class="m-0">BizConsult</h1> -->
      <img src="@/assets/img/icasee_logo_white.webp" alt="Logo" id="logoImage" />
    </a>
    <button
      class="navbar-toggler"
      type="button"
      data-bs-toggle="collapse"
      data-bs-target="#navbarCollapse"
    >
      <span class="fa fa-bars"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarCollapse">
      <div class="navbar-nav ms-auto py-0">
        <a href="index.html" class="nav-item nav-link active">Home</a>
        <div class="nav-item dropdown">
          <a
            href="pages/readMore/aboutTheEvent.html"
            class="nav-link dropdown-toggle"
            data-bs-toggle="dropdown"
            >About</a
          >
          <div class="dropdown-menu m-0">
            <a href="pages/aboutSubPages/photoGallery.html" class="dropdown-item">Photo Gallery</a>
            <a href="pages/aboutSubPages/erbilCity.html" class="dropdown-item">Erbil City</a>
            <a href="pages/aboutSubPages/accomodation.html" class="dropdown-item">Accommodation</a>
            <a href="pages/aboutSubPages/archives.html" class="dropdown-item">Archives</a>
            <a href="pages/aboutSubPages/sponsors.html" class="dropdown-item">Sponsors</a>
            <a href="pages/aboutSubPages/travelVisa.html" class="dropdown-item">Travel/Visa</a>
          </div>
        </div>
        <a href="pages/subPages/committees.html" class="nav-item nav-link">Committes</a>

        <!-- <a href="pages/subPages/authorGuidelines.html" class="nav-item nav-link">Author Guidlines</a> -->

        <div class="nav-item dropdown">
          <a href="" class="nav-link dropdown-toggle" data-bs-toggle="dropdown">Guidelines</a>
          <div class="dropdown-menu m-0">
            <a href="pages/guidelinesSubPages/fullPaperSubmission.html" class="dropdown-item"
              >Full Paper Submission</a
            >
            <a href="pages/guidelinesSubPages/callForPaper.html" class="dropdown-item"
              >Call for Paper</a
            >
            <a href="pages/guidelinesSubPages/importantDates.html" class="dropdown-item"
              >Important Dates</a
            >
            <a href="pages/guidelinesSubPages/abstractTemplate.html" class="dropdown-item"
              >Abstract Template</a
            >
            <a href="pages/guidelinesSubPages/scope.html" class="dropdown-item">Scope</a>
            <a href="pages/guidelinesSubPages/downloadCenter.html" class="dropdown-item"
              >Download Center</a
            >
          </div>
        </div>

        <a href="pages/subPages/program.html" class="nav-item nav-link">Program</a>
        <a href="pages/subPages/fees.html" class="nav-item nav-link">Fees</a>
      </div>
      <a
        href="pages/subPages/registration.html"
        class="btn btn-light rounded-pill text-primary py-2 px-4 ms-lg-5"
        >Registration</a
      >
    </div>
  </nav>
  <!-- Navbar End -->
</template>

<style scoped>
/*** Navbar ***/
.navbar .navbar-nav .nav-link {
  position: relative;
  margin-left: 25px;
  padding: 35px 0;
  color: #ffffff;
  font-weight: 500;
  outline: none;
  transition: 0.5s;
}

.navbar .navbar-nav .nav-link:hover,
.navbar .navbar-nav .nav-link.active {
  color: #ffffff;
}

.sticky-top.navbar .navbar-nav .nav-link {
  padding: 20px 0;
  color: var(--dark);
}

.sticky-top.navbar .navbar-nav .nav-link:hover,
.sticky-top.navbar .navbar-nav .nav-link.active {
  color: var(--primary);
}

.navbar .navbar-brand h1 {
  color: #ffffff;
}

.navbar .navbar-brand img {
  max-height: 60px;
  transition: 0.5s;
}

.sticky-top.navbar .navbar-brand img {
  max-height: 45px;
}

/* In this case, the styles will be applied if the width of the viewport is 991.98 pixels or smaller. */
@media (max-width: 991.98px) {
  .sticky-top.navbar {
    position: relative;
    background: #ffffff;
  }

  .navbar .navbar-collapse {
    margin-top: 15px;
    border-top: 1px solid #dddddd;
  }

  .navbar .navbar-nav .nav-link,
  .sticky-top.navbar .navbar-nav .nav-link {
    padding: 10px 0;
    margin-left: 0;
    color: var(--dark);
  }

  .navbar .navbar-nav .nav-link:hover,
  .navbar .navbar-nav .nav-link.active {
    color: var(--primary);
  }

  .navbar .navbar-brand h1 {
    color: var(--primary);
  }

  .navbar .navbar-brand img {
    max-height: 45px;
  }
  /* My Code */
}

/* In this case, the styles will be applied if the width of the viewport is 992 pixels or larger. */
@media (min-width: 992px) {
  .navbar {
    position: absolute;
    width: 100%;
    top: 0;
    left: 0;
    border-bottom: 1px solid rgba(256, 256, 256, 0.2);
    z-index: 999;
  }

  .sticky-top.navbar {
    position: fixed;
    background: #ffffff;
  }

  .navbar .navbar-nav .nav-link::before {
    position: absolute;
    content: '';
    width: 100%;
    height: 2px;
    bottom: 10px;
    left: 0;
    background: #ffffff;
    opacity: 0;
    transition: 0.5s;
  }

  .sticky-top.navbar .navbar-nav .nav-link::before {
    background: var(--primary);
  }

  .navbar .navbar-nav .nav-link:hover::before,
  .navbar .navbar-nav .nav-link.active::before {
    bottom: -1px;
    left: 0;
    opacity: 1;
  }

  .navbar .navbar-nav .nav-link.nav-contact::before {
    display: none;
  }

  .sticky-top.navbar .navbar-brand h1 {
    color: var(--primary);
  }

  .navbar .nav-item .dropdown-menu {
    display: block;
    visibility: hidden;
    top: 100%;
    transform: rotateX(-75deg);
    transform-origin: 0% 0%;
    transition: 0.5s;
    opacity: 0;
  }

  .navbar .nav-item:hover .dropdown-menu {
    transform: rotateX(0deg);
    visibility: visible;
    transition: 0.5s;
    opacity: 1;
  }
}
</style>
