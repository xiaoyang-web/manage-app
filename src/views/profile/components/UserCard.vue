<template>
  <el-card style="margin-bottom:20px;">
    <div slot="header" class="clearfix">
      <span>关于</span>
    </div>

    <div class="user-profile">
      <div class="box-center">
        <pan-thumb :image="user.avatar" :height="'100px'" :width="'100px'" :hoverable="false">
          <div>Hello</div>
          {{ user.name }}
        </pan-thumb>
      </div>
      <div class="box-center">
        <div class="user-name text-center">{{ user.name }}</div>
      </div>
    </div>

    <div class="user-bio">
      <div class="user-phone user-bio-section">
        <div class="user-bio-section-header">
          <svg-icon icon-class="phone" /><span>电话</span>
        </div>
        <div class="user-bio-section-body">
          <p class="text-muted">
            {{ user.phone }}
          </p>
        </div>
      </div>

      <div class="user-email user-bio-section">
        <div class="user-bio-section-header">
          <svg-icon icon-class="email" /><span>邮箱</span>
        </div>
        <div class="user-bio-section-body">
          <p class="text-muted">
            {{ user.email }}
          </p>
        </div>
      </div>

      <div class="user-github user-bio-section">
        <div class="user-bio-section-header">
          <svg-icon icon-class="github" /><span>github</span>
        </div>
        <div class="user-bio-section-body">
          <p class="text-muted">
            <a href="https://github.com/xiaoyang-web/manage-app">项目地址</a>
          </p>
        </div>
      </div>
    </div>
  </el-card>
</template>

<script>
import PanThumb from '@/components/PanThumb'
// import clipboard from '@/directive/clipboard/index.js'

export default {
  components: { PanThumb },
  props: {
    user: {
      type: Object,
      default: () => {
        return {
          name: '',
          phone: '',
          email: '',
          avatar: '',
          role: ''
        }
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.box-center {
  margin: 0 auto;
  display: table;
}

.text-muted {
  color: #777;
}

.user-profile {
  .user-name {
    font-weight: bold;
  }

  .box-center {
    padding-top: 10px;
  }

  .user-role {
    padding-top: 10px;
    font-weight: 400;
    font-size: 14px;
  }

  .box-social {
    padding-top: 30px;

    .el-table {
      border-top: 1px solid #dfe6ec;
    }
  }

  .user-follow {
    padding-top: 20px;
  }
}

.user-bio {
  margin-top: 20px;
  color: #606266;

  span {
    padding-left: 4px;
  }

  .user-bio-section {
    font-size: 14px;
    padding: 15px 0;

    .user-bio-section-header {
      border-bottom: 1px solid #dfe6ec;
      padding-bottom: 10px;
      margin-bottom: 10px;
      font-weight: bold;
      cursor: pointer;
    }
  }
}
</style>
