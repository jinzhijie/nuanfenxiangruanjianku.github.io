<template>
  <div id="links" class="share-links">
    <b-spinner
      class="loadingIcon"
      label="Loading..."
      v-if="loadingContent"
    ></b-spinner>
    <b-skeleton-wrapper animation="throb" :loading="loadingContent">
      <b-row class="link-cards" v-if="!loadingContent">
        <b-col sm="4" v-for="content in linkContents" :key="content.link"
          ><b-card tag="article" class="mb-2" no-body>
            <b-card-body>
              <b-card-title
                ><b-badge v-if="content.badge" v-text="content.badge"></b-badge>
                {{ content.name }}</b-card-title
              >
              <b-card-text v-if="content.desc" v-text="content.desc">
              </b-card-text>
              <b-button
                :href="content.link"
                target="_blank"
                variant="primary"
                v-text="content.buttonText"
              ></b-button>
            </b-card-body> </b-card
        ></b-col>
      </b-row>
    </b-skeleton-wrapper>
  </div>
</template>

<script>
  export default {
    name: 'Links',
    data() {
      return {
        loadingContent: true,
        linkContents: [],
      };
    },
    created() {
      this.$bvToast.toast('点击工具栏，立即收藏我们的网站！', {
        title: '欢迎来到暖分享软件库',
        autoHideDelay: 3000,
        appendToast: true,
        toaster: 'b-toaster-bottom-center'
      });
      // get configure
      this.$axios
        .get('links.json')
        .then((response) => {
          this.linkContents = response.data;
          this.loadingContent = false;
        })
        .catch((error) => {
          this.$bvToast.toast(`加载分享列表时产生了错误，因为 ${error}`, {
            title: '☹ 出错了',
            autoHideDelay: 10000,
            variant: 'warning',
            toaster: 'b-toaster-top-center',
            appendToast: true,
          });
        });
    },
  };
</script>

<style>
  .share-links {
    padding: 1rem;
  }
  .loadingIcon {
    margin: auto;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
  }
</style>
