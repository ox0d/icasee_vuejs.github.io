<script setup></script>

<template>
  <div class="container-xxl bg-primary hero-header">
    <div class="container">
      <div class="row g-5 justify-content-center">
        <div class="col-12 col-lg-6" id="hero_title_english_kurdish_arabic">
          <h1 class="text-white pb-3 animated zoomIn">
            7th International Conference on Applied Science, Energy and Environment
          </h1>

          <h5 class="text-white pb-3 animated zoomIn">
            حەوتەمین کۆنفرانسی نێودەوڵەتی بۆ زانستی کارەکی و وزە و ژینگە
          </h5>
          <h5 class="text-white pb-3 animated zoomIn">
            المؤتمر السابع الدولي للعلوم التطبيقية والطاقة والبيئة
          </h5>
          <p class="text-white pb-3 animated zoomIn">June 22-24, 2024 - Erbil, KRG, Iraq</p>
          <div class="row">
            <div class="col-12 col-md-6 text-center pb-3">
              <a
                href="pages/guidelinesSubPages/callForPaper.html"
                class="btn btn-outline-light rounded-pill border-2 py-3 px-3 animated slideInRight"
                >Call for Paper and Publication</a
              >
            </div>
            <div class="col-12 col-md-6 text-center">
              <a
                href="pages/readMore/importantNews.html"
                class="btn btn-outline-light rounded-pill border-2 py-3 px-4 animated slideInRight"
                >Important News</a
              >
            </div>
          </div>
        </div>
        <div class="col-12 col-lg-6">
          <img class="img-fluid animated zoomIn" src="@/assets/img/hero1.png" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/*** Hero Header ***/
.hero-header {
  margin-bottom: 6rem;
  padding: 10rem 0 8rem 0;
  background: url(@/assets/img/shape-bottom2_v0.1.png) center bottom no-repeat;
}

.page-header {
  margin-bottom: 6rem;
  padding: 12rem 0 6rem 0;
}

@media (max-width: 991.98px) {
  .hero-header {
    padding: 6rem 0 9rem 0;
  }

  .page-header {
    padding: 6rem 0;
  }
}

.page-header .breadcrumb-item + .breadcrumb-item::before {
  color: rgba(256, 256, 256, 0.5);
}
</style>
