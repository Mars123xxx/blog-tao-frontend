<template>
  <header class="navbar-light fixed-top">
  </header>
  <main>
    <div class="container">
      <div class="row g-4">
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
                <p class="small text-center mt-1">©2023 <a class="text-reset" target="_blank" href="https://www.webestica.com/"> Webestica </a></p>
              </div>
            </div>
          </nav>
        </div>
        <div class="col-md-8 col-lg-6 vstack gap-4">
          <el-card>
            <template #header>
              <div class="card-header">
                <el-row class="avatar-info">
                  <el-avatar round src="https://profile-1317403776.cos.ap-beijing.myqcloud.com/default_user.jpg"></el-avatar>
                  <div class="mx-2 d-flex flex-column justify-content-between">
                    <span class="avatar-name">孰是孰非</span>
                    <span class="post-time">5 min ago</span>
                  </div>
                </el-row>
              </div>
            </template>
            <template #default>
              <div class="text-black-50">天堂太远，人间太近</div>
              <div class="demo-image__lazy">
                <el-image
                    :src="url"
                    v-for="url in srcList" lazy
                />
              </div>
              <div class="toolbox d-flex justify-content-between mt-2 pt-2">
                <div class="like-comment">
                  <el-tooltip
                      class="box-item"
                      effect="light"
                      content="点赞"
                      placement="bottom"
                  >
                    <el-icon size="25" color="red"><StarFilled /></el-icon>
                  </el-tooltip>
                  <span>3000</span>
                  <el-tooltip
                      class="box-item"
                      effect="light"
                      content="评论"
                      placement="bottom"
                  >
                    <el-icon size="20"><Flag /></el-icon>
                  </el-tooltip>
                  <span>140</span>
                </div>
                <el-tooltip
                    class="box-item"
                    effect="light"
                    content="转发"
                    placement="bottom"
                >
                  <el-icon size="20"><Share /></el-icon>
                </el-tooltip>
              </div>
            </template>
            <template #footer>Footer content</template>
          </el-card>
        </div>
        <div class="col-lg-3">
          <div class="row g-4">
            <div class="col-sm-6 col-lg-12">
              <el-card>
                <el-button @click="this.$message('你好啊')">点我</el-button>
              </el-card>
            </div>
            <div class="col-sm-6 col-lg-12">
              <el-card>
                <el-button @click="this.$message({message:'别点我',type:'success'})">点我</el-button>
              </el-card>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import {ref} from "vue";
import {ChatLineRound, Flag, Share, StarFilled} from "@element-plus/icons-vue";
const srcList = [
  'https://fuss10.elemecdn.com/a/3f/3302e58f9a181d2509f3dc0fa68b0jpeg.jpeg',
  'https://fuss10.elemecdn.com/1/34/19aa98b1fcb2781c4fba33d850549jpeg.jpeg',
  'https://fuss10.elemecdn.com/0/6f/e35ff375812e6b0020b6b4e8f9583jpeg.jpeg',
  'https://fuss10.elemecdn.com/9/bb/e27858e973f5d7d3904835f46abbdjpeg.jpeg',
  'https://fuss10.elemecdn.com/d/e6/c4d93a3805b3ce3f323f7974e6f78jpeg.jpeg',
  'https://fuss10.elemecdn.com/3/28/bbf893f792f03a54408b3b7a7ebf0jpeg.jpeg',
  'https://fuss10.elemecdn.com/2/11/6535bcfb26e4c79b48ddde44f4b6fjpeg.jpeg',
]
</script>

<style lang="scss" scoped>
.avatar-info{
  .avatar-name{
    font-size: 0.8rem;
    font-weight: bold;
  }
  .post-time{
    font-size: 0.7rem;
  }
}

.toolbox{
  .like-comment{
    span{
      font-size: 0.6rem;
    }
    .el-icon{
      margin-left: 1rem;
    }
  }
  border-top: aquamarine solid 1px;
}

.el-card {
  :deep .el-card__body{
    padding-bottom: 5px !important;
    border: none;
  }
  :deep .el-card__footer{
    border: none;
  }
}

.demo-image__lazy {
  height: 300px;
  overflow-y: auto;
}
.demo-image__lazy .el-image {
  display: block;
  min-height: 200px;
  margin-bottom: 10px;
}
.demo-image__lazy .el-image:last-child {
  margin-bottom: 0;
}
</style>