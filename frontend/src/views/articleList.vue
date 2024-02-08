<template>
  <header class="navbar-light fixed-top">
  </header>
  <main>
    <div class="container">
      <div class="row g-4">
        <left-block></left-block>
        <div class="col-md-8 col-lg-6 vstack gap-4">
          <el-card>
            <template #header>
              <div class="card-header">
                <el-row class="avatar-info">
                  <el-avatar round src="https://profile-1317403776.cos.ap-beijing.myqcloud.com/default_user.jpg" class="avatar"></el-avatar>
                  <div class="mx-2 d-flex flex-column justify-content-between">
                    <span class="avatar-name">孰是孰非</span>
                    <span class="post-time">5 min ago</span>
                  </div>
                </el-row>
              </div>
            </template>
            <template #default>
              <div class="text-black-50">copyLink(val) { // 复制链接
                console.log(val, '复制链接')
                let url = val // 后台接口返回的链接地址
                let inputNode = document.createElement('input')  // 创建input
                inputNode.value = url // 赋值给 input 值
                document.body.appendChild(inputNode) // 插入进去
                inputNode.select() // 选择对象
                document.execCommand('Copy') // 原生调用执行浏览器复制命令
                inputNode.className = 'oInput'
                inputNode.style.display = 'none' // 隐藏
                this.$message.success('复制成功')
                },
              </div>
              <div class="demo-image__lazy" v-if="false">
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
                  <el-button circle @click="likeArticle(0)" :style="{'background': haslike ? '#D7BBBA' : ''}">
                      <i class="bi bi-hand-thumbs-up" v-show="likenumshow"></i>
                      <span v-show="!likenumshow">3000</span>
                  </el-button>
                  </el-tooltip>
                  <el-tooltip
                      class="box-item"
                      effect="light"
                      content="评论"
                      placement="bottom"
                  >
                  <el-button circle @click="commentArticle(0)">
                    <i class="bi bi-chat-dots" v-show="commentnumshow"></i>
                    <span v-show="!commentnumshow">140</span>
                  </el-button>
                  </el-tooltip>
                </div>
                <el-tooltip
                    class="box-item"
                    effect="light"
                    content="转发"
                    placement="bottom"
                >
                  <el-button circle @click="shareAricle(0)">
                    <i class="bi bi-app-indicator" v-show="sharenumshow"></i>
                    <span v-show="!sharenumshow">400</span>
                  </el-button>
                </el-tooltip>
              </div>

            </template>
            <template #footer>
              <el-row v-show="comment" justify="space-around" :gutter="15">
                <el-col :span="2">
                  <el-popover trigger="click" ref="popoverRef">
                    <div class="emojiBox">
                      <ul>
                        <li
                            v-for="(item, index) in emoji.faceList"
                            :key="index"
                            @click="getEmoji(index)"
                        >
                          {{ item }}
                        </li>
                      </ul>
                    </div>
                    <template #reference>
                      <el-button>
                        <el-icon><Promotion /></el-icon>
                      </el-button>
                    </template>
                  </el-popover>

                </el-col>
                <el-col :span="16">
                  <el-input v-model="input" placeholder="写下您的评论~" type="textarea" autosize autofocus resize="none"/>
                </el-col>
                <el-col :span="4">
                  <el-button type="primary" plain>发送</el-button>
                </el-col>
              </el-row>
              <div v-for="i in 2">
                <el-row justify="space-around" class="comment-box" :gutter="0">
                  <el-col :span="3">
                    <div class="d-flex flex-column" style="width: min-content">
                      <el-avatar round src="https://profile-1317403776.cos.ap-beijing.myqcloud.com/default_user.jpg" class="avatar"></el-avatar>
                      <span class="font-size-12 comment-user">孰是孰非</span>
                    </div>
                  </el-col>
                  <el-col :span="20">
                    <div class="font-size-12 comment-info">哈哈哈，真是一个小机灵鬼，啦啦啦啦时代峰峻阿萨德飞机阿萨方式打开放假啦收到回复拉萨代发立卡jlaksdjflajsdlfjalsjdfljasdflaksdjflkasdjfklasjdflkajsdlkfjlasjdfjljkdjkafshdkhfaskldhfalsdddddddfffffffffffffffffffffff</div>
                  </el-col>
                  <el-col :span="1">
                    <div class="d-flex flex-column h-100 justify-content-end">
                      <i class="bi bi-hand-thumbs-up"></i>
                    </div>
                  </el-col>
                </el-row>
              </div>

            </template>
          </el-card>
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
                    <el-icon size="25" :color="like ? 'red' : '' " @click="likeArticle(0)"><StarFilled /></el-icon>
                  </el-tooltip>
                  <span>3000</span>
                  <el-tooltip
                      class="box-item"
                      effect="light"
                      content="评论"
                      placement="bottom"
                  >
                    <el-icon size="20" :color="comment ? '#68C3F1' : '' " @click="comment=!comment"><Flag /></el-icon>
                  </el-tooltip>
                  <span>140</span>
                </div>
                <el-tooltip
                    class="box-item"
                    effect="light"
                    content="转发"
                    placement="bottom"
                >

                  <el-icon size="20" @click="shareAricle(0)"><Share /></el-icon>
                </el-tooltip>
              </div>

            </template>
            <template #footer>
              <el-row v-show="comment" justify="space-around" :gutter="15">
                <el-col :span="2">
                  <el-popover trigger="click" ref="popoverRef">
                    <div class="emojiBox">
                      <ul>
                        <li
                            v-for="(item, index) in emoji.faceList"
                            :key="index"
                            @click="getEmoji(index)"
                        >
                          {{ item }}
                        </li>
                      </ul>
                    </div>
                    <template #reference>
                      <el-button>
                        <el-icon><Promotion /></el-icon>
                      </el-button>
                    </template>
                  </el-popover>

                </el-col>
                <el-col :span="16">
                  <el-input v-model="input" placeholder="写下您的评论~" type="textarea" autosize autofocus resize="none"/>
                </el-col>
                <el-col :span="4">
                  <el-button type="primary" plain>发送</el-button>
                </el-col>
              </el-row>
              <div v-for="i in 2">
                <el-row justify="space-evenly">
                  <el-col :span="4">
                    <div class="d-flex flex-column" style="width: min-content">
                      <el-avatar round src="https://profile-1317403776.cos.ap-beijing.myqcloud.com/default_user.jpg"></el-avatar>
                      <span class="font-size-12 comment-user">孰是孰非</span>
                    </div>
                  </el-col>
                  <el-col :span="18">
                    <span class="font-size-12 comment-info">哈哈哈，真是一个小机灵鬼，啦啦啦啦时代峰峻阿萨德飞机阿萨方式打开放假啦收到回复拉萨代发立卡jlaksdjflajsdlfjalsjdfljasdflaksdjflkasdjfklasjdflkajsdlkfjlasjdfjljkdjkafshdkhfaskldhfalsdddddddfffffffffffffffffffffff</span>
                  </el-col>
                </el-row>
              </div>

            </template>
          </el-card>
        </div>
        <right-block></right-block>
      </div>
    </div>
  </main>
</template>

<script setup>
import useClipboard from 'vue-clipboard3'
import {computed, onMounted, ref} from "vue";
import emojiJson from "../assets/emoji/emoji.json";
import {
  ChatLineRound,
  CircleCheck,
  CollectionTag,
  Flag,
  GobletSquare,
  Promotion,
  Share,
  StarFilled
} from "@element-plus/icons-vue";
import {ElMessage} from "element-plus";
import LeftBlock from "../components/leftBlock.vue";
import RightBlock from "../components/rightBlock.vue";
const srcList = [
  'https://fuss10.elemecdn.com/a/3f/3302e58f9a181d2509f3dc0fa68b0jpeg.jpeg',
  'https://fuss10.elemecdn.com/1/34/19aa98b1fcb2781c4fba33d850549jpeg.jpeg',
  'https://fuss10.elemecdn.com/0/6f/e35ff375812e6b0020b6b4e8f9583jpeg.jpeg',
  'https://fuss10.elemecdn.com/9/bb/e27858e973f5d7d3904835f46abbdjpeg.jpeg',
  'https://fuss10.elemecdn.com/d/e6/c4d93a3805b3ce3f323f7974e6f78jpeg.jpeg',
  'https://fuss10.elemecdn.com/3/28/bbf893f792f03a54408b3b7a7ebf0jpeg.jpeg',
  'https://fuss10.elemecdn.com/2/11/6535bcfb26e4c79b48ddde44f4b6fjpeg.jpeg',
]
const comment = ref(false)
const input = ref('')
const like = ref(false)
const emoji = ref({
  //表情列表
  faceList: [],
})
const likenumshow = ref(true)
const commentnumshow = ref(true)
const sharenumshow = ref(true)
const haslike = ref(false)
const popoverRef = ref(null)
function loadEmojis() {
  for (let i in emojiJson) {
    emoji.value.faceList.push(emojiJson[i].char);
  }
}
function getEmoji(index){
  input.value += emoji.value.faceList[index];
  popoverRef.value.hide()
}

function likeArticle(index){
  like.value =!like.value
  likenumshow.value=!likenumshow.value;
  setTimeout(()=>{likenumshow.value=!likenumshow.value},2000)
  haslike.value = !haslike.value
}

function commentArticle(index){
  comment.value =!comment.value
  commentnumshow.value=!commentnumshow.value;
  setTimeout(()=>{commentnumshow.value=!commentnumshow.value},2000)
}

function shareAricle(index){
  const { toClipboard } = useClipboard()
  const copy = async () => {
    try {
      await toClipboard(index)
    } catch (e) {
      console.error(e)
    }
  }
  copy()
  sharenumshow.value=!sharenumshow.value;
  setTimeout(()=>{sharenumshow.value=!sharenumshow.value},2000)
  ElMessage({message:'复制链接成功！',type:'success'})
}

onMounted(function (){
  loadEmojis()
})

</script>

<style lang="scss" scoped>
.comment-box{
  .comment-user{
    width: max-content;
  }
  .comment-info{
    max-width: max-content;
    word-break: break-all;
    background-color: antiquewhite;
    padding: 0.5rem;
    border-radius: 0.5rem;
    word-spacing: 0.5rem;
  }
  margin: 0.8rem 0;
}

.font-size-12{
  font-size: 0.7rem !important;
}
.emojiBox {
  width: 25rem;
  height: 200px;
  background: #e6e6e6;
  position: absolute;
  z-index: 100;
  bottom: 0;
  overflow: scroll;
  ul {
    display: flex;
    flex-wrap: wrap;
    padding: 10px;
    li {
      cursor: pointer;
      width: 10%;
      font-size: 26px;
      list-style: none;
      text-align: center;
    }
    li:hover {
      background: #fff;
    }
  }
}

.avatar:hover{
  transform: scale(1.2); /*缩放大小*/
  filter: brightness(110%);
}

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
  span{
    font-size: 0.6rem;
  }
  .like-comment{
    .el-icon{
      margin-left: 1rem;
    }
  }
  border-top: aquamarine solid 1px;
}

.el-card {
  :deep(.el-card__body){
    padding-bottom: 5px !important;
    border: none;
  }
  :deep(.el-card__footer){
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