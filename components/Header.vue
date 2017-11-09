<template>
  <div class="header">
    <el-menu :default-active="activeIndex" mode="horizontal" @select="handleSelect">
      <div class="header-logo">
        <nuxt-link to="/"><img class="logo" src="logo.png"/></nuxt-link>
      </div>
      <el-submenu class="header-menu" index="1">
        <template slot="title">メニュー</template>
        <el-menu-item index="about">Mableとは？</el-menu-item>
        <el-menu-item index="preview">データを切り取る</el-menu-item>
      </el-submenu>
      <el-menu-item index="login">ログイン/新規会員登録</el-menu-item>
      <!--<el-button v-popover:account>ynunokawa</el-button>
      <el-popover
        ref="account"
        placement="right"
        width="400"
        trigger="click">
        <p>ここにアカウント情報が入る</p>
      </el-popover>-->
    </el-menu>
  </div>
</template>

<script>
import { Menu, MenuItem, Submenu, Popover, Button } from 'element-ui'

export default {
  data () {
    return {
      activeIndex: '1',
      activeIndex2: '1'
    }
  },
  components: {
    'el-menu': Menu,
    'el-menu-item': MenuItem,
    'el-submenu': Submenu,
    'el-popover': Popover,
    'el-button': Button
  },
  methods: {
    handleSelect (key, keyPath) {
      console.log(key, keyPath)
      location.href = `/${key}`
    }
  }
}
</script>

<style>
.header {
  position: fixed;
  width: 100%;
  z-index: 9;
}

.el-menu {
  display: flex;
}

.logo {
  height: 56px;
}

.header-logo {
  margin: 0 20px;
}

.header-menu {
  outline: none;
}

.el-menu--horizontal .el-submenu > .el-menu {
  display: block;
}
</style>
