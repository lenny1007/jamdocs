<template>
  <Layout :sidebar="false">
    <div class="content">
      <h1>{{ $static.metadata.siteName }}</h1>
      <h2> {{ this.description }}</h2>
      <nav>
        <!-- To use other icons here, you need to import them in the Shortcut component -->
        <Shortcut link="/gene-make-you-bold" text="為什麼掉頭髮 ?" icon="trending-down-icon" />
        <Shortcut link="/minoxidil-solution-foam" text="有效的生髮產品" icon="award-icon" />
        <Shortcut link="/minoxidil-personal-experience" text="經驗分享" icon="user-icon" />
      </nav>
      <p></p>
      <nav>
      <Shortcut link="/drug-for-hairloss" text="口服藥物" icon="help-circle-icon" />
      <Shortcut link="/choose-shampoo" text="洗髮精的選擇" icon="check-circle-icon" />
      <Shortcut link="/about-wig" text="假髮、植髮" icon="dollar-sign-icon" />
      </nav>

      <div class = "line-link">
      <img src="https://scdn.line-apps.com/n/line_add_friends/btn/zh-Hant.png" alt="加入好友" height="36" border="0"></a>
      <h4>加入RK咻咻代買好友，救頭髮救錢包。</h4> <a href="https://lin.ee/mLkGDK7">

      </div>
       <!-- <GitLink class="git" size="large" /> -->
    </div>
  </Layout>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
import GitLink from '~/components/GitLink.vue'
import Shortcut from '~/components/Shortcut.vue'

export default {
  components: {
    GitLink,
    Shortcut
  },
  data() {
    return {
      description: ' 讓您在抗禿長頭髮路上不花冤枉錢 ! '
    }
  },
  metaInfo() {
    return {
      title: this.description,
      meta: [
        { key: 'description', name: 'description', content: '讓您在抗禿長頭髮路上不花冤枉錢 !' }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.content {
  display: flex;
  flex-direction: column;
}

h1 {
  text-align: center;
  max-width: 600px;
  margin: 1.5em auto 0.5em;

  @include respond-above(md) {
    max-width: 1000px;
  }
}

h2 {
  text-align: center;
  margin: 0 auto 1.5em;
}

.line-link {
  text-align: center;
  margin: 1.5em auto 1.5em;
}

nav {
  display: flex;
  justify-content: space-between;
  flex-direction: column;

  @include respond-above(sm) {
    flex-direction: row;
  }
}

.git {
  margin: 3em 0 0;
  align-self: center;

  @include respond-above(md) {
    margin: 5em 0 0;
  }
}
</style>
