<template>
  <div id="app">
    <b-navbar toggleable="lg" type="dark" variant="info">
      <b-navbar-brand href="#">暖分享软件库</b-navbar-brand>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <b-navbar-nav>
            <b-nav-item v-b-modal.modal-contact href="#">联系我们</b-nav-item>
            <b-nav-item v-b-modal.modal-aboutus href="#">关于</b-nav-item>
          </b-navbar-nav>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
    <b-modal id="modal-contact" title="联系我们 - 暖分享软件库" hide-footer>
      <p>合作 / 投稿 / 意见 / 反馈版权问题等，请使用以下方式联系我</p>
      <p>
        QQ：<code>2231143581</code><br />
        微信：<code>nuanrjk0</code><br />
      </p> </b-modal
    ><b-modal id="modal-aboutus" title="关于 - 暖分享软件库" hide-footer>
      <p>
        暖分享团队感谢大家的长期关注和支持，今后我们会用更多的福利回报大家。强烈建议收藏本页面！
      </p>
      <p>
        获取更多资源资讯：加入官方 QQ 群
        <b-link href="https://sourl.cn/kHPDhY" target="_blank"
          ><code>57699656</code></b-link
        >
      </p>
      <p style="font-size: 8px; text-align: center;">橘猫云 提供技术支持</p>
    </b-modal>
    <!-- Cards -->
    <Links />
    <!-- Tips -->
    <div class="tips">
      <b-alert v-model="showUsageInfo" variant="info" dismissible>
        若无法下载软件，请复制链接到浏览器打开下载。<br />
        若部分软件打开时出现闪退的情况，直接卸载即可。<br />
        部分陈旧的软件可能已经失效，欢迎加入我们的官方群以获取最新资讯！
      </b-alert>
      <b-alert show style="text-align: center;"
        >立即加入官方 QQ 群
        <b-link href="https://sourl.cn/kHPDhY" target="_blank"
          ><code>57699656</code></b-link
        >
      </b-alert>
    </div>
  </div>
</template>

<script>
  import Links from './components/Links';
  export default {
    name: 'App',
    data() {
      return {
        showUsageInfo: true,
      };
    },
    components: {
      Links,
    },
  };
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

  .tips {
    text-align: left;
    padding-left: 1rem;
    padding-right: 1rem;
  }
</style>
