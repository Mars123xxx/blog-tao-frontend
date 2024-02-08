<template>
  <div class="col-lg-3">
    <div class="d-flex align-items-center d-lg-none">
      <button class="border-0 bg-transparent" data-bs-toggle="offcanvas" data-bs-target="#offcanvasSideNavbar" aria-controls="offcanvasSideNavbar">
        <span class="btn btn-primary"><i class="bi bi-sliders2"></i>哈哈</span>
        <span class="h6 mb-0 fw-bold d-lg-none ms-2">个人信息</span>
      </button>
    </div>
    <nav class="navbar navbar-expand-lg mx-0">
      <div class="offcanvas offcanvas-start" tabindex="-1" id="offcanvasSideNavbar">
        <!-- Offcanvas header -->
        <div class="offcanvas-header">
          <button type="button" class="btn-close text-reset ms-auto" data-bs-dismiss="offcanvas" aria-label="Close"></button>
        </div>

        <!-- Offcanvas body -->
        <div class="offcanvas-body d-block px-2 px-lg-0">
          <!-- Card START -->
          <div class="card overflow-hidden">
            <!-- Cover image -->
            <div class="h-50px"></div>
            <!-- Card body START -->
            <div class="card-body pt-0">
              <div class="text-center">
                <!-- Avatar -->
                <div class="avatar avatar-lg mt-n5 mb-3">
                  <a href="#!"><img class="avatar-img rounded border border-white border-3" src="" alt=""></a>
                </div>
                <!-- Info -->
                <h5 class="mb-0"> <a href="#">Sam Lanson </a></h5>
                <small>Web Developer at Webestica</small>
                <p class="mt-3">I'd love to change the world, but they won’t give me the source code.</p>

                <!-- User stat START -->
                <div class="hstack gap-2 gap-xl-3 justify-content-center">
                  <!-- User stat item -->
                  <div>
                    <h6 class="mb-0">256</h6>
                    <small>Post</small>
                  </div>
                  <!-- Divider -->
                  <div class="vr"></div>
                  <!-- User stat item -->
                  <div>
                    <h6 class="mb-0">2.5K</h6>
                    <small>Followers</small>
                  </div>
                  <!-- Divider -->
                  <div class="vr"></div>
                  <!-- User stat item -->
                  <div>
                    <h6 class="mb-0">365</h6>
                    <small>Following</small>
                  </div>
                </div>
                <!-- User stat END -->
              </div>

              <!-- Divider -->
              <hr>

              <!-- Side Nav START -->
              <ul class="nav nav-link-secondary flex-column fw-bold gap-2">
                <li class="nav-item">
                  <a class="nav-link" href="blog.html"> <span>Latest News </span></a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="notifications.html"><span>Notifications </span></a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="settings.html"><span>Settings </span></a>
                </li>
              </ul>
              <!-- Side Nav END -->
            </div>
          </div>
          <!-- Card END -->

          <!-- Copyright -->
          <p class="small text-center mt-1">©2023 <a class="text-reset" target="_blank" href="https://blog.taotaohan.love"> 陶陶涵 </a></p>
        </div>
      </div>
    </nav>
  </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>

</style>