<template>
  <div class="wrapper">
  <Header/>
    <section class="latest__posts">
      <article class="article">
        <div class="single">
          <h1 class="post-title">{{ post.fields.title }}</h1>
          <p class="post-created-at">{{ formatDate(post.sys.createdAt) }}</p>
          <div class="post-content" v-html="$md.render(post.fields.content)"></div>
        </div>
      </article>
      <Aside/>
    </section>
  <Footer/>
  </div>
</template>

<script>
import client from '~/plugins/contentful'
import Header from '../../components/Header';
import Footer from '../../components/Footer';
import Aside from '../../components/Aside';
export default {
  components : {
    Header,
    Footer,
    Aside,
  },
  asyncData({ params, error, payload }) {
    if (payload) return { post: payload }
    return client
      .getEntries({
        content_type: 'post',
        'fields.slug': params.slug,
      })
      .then(entries => {
        return { post: entries.items[0] }
      })
      .catch(e => console.log(e))
  },
  head() {
    return {
      title: this.post.fields.title,
    }
  },
  mounted() {
    console.log(this.post)
  },
  methods: {
    formatDate(iso) {
      const date = new Date(iso)
      const yyyy = new String(date.getFullYear())
      const mm = new String(date.getMonth() + 1).padStart(2, "0")
      const dd = new String(date.getDate()).padStart(2, "0")
      return `${yyyy}.${mm}.${dd}`
    }
  }
}
</script>

<style lang="scss">
article.article {
  width: percentage(800/1200);
  margin: 0 auto 0 0;
  padding: 10px;
  .single {
    max-width: 900px;
    margin: 0 auto;
    padding: 10px;
    color: #222;
    border: 2px solid #444;
    border-radius: 10px;
    h1, h2, h3 {
      margin: 16px 0;
    }
    h1.post-title {
      font-size: 32px;
      text-decoration: underline;
    }
    .post-content {
      h1 {
        font-size: 32px;
      }
      h2 {
        font-size: 24px;
        background: #ccc
      }
      p {
        margin: 16px 0;
        font-size: 16px;
      }
      img {
        max-width: 100%;
        border: 1px solid #000;
      }
    }
  }
}
</style>
