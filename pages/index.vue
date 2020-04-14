<template>
  <div class="wrapper">
  <Header/>
    <section class="latest__posts">
      <div class="posts">
        <nuxt-link :to="'posts/'+post.fields.slug" class="post" v-for="(post, index) in posts" :key="index">
          <div class="thumb">
            <img :src="post.fields.image.fields.file.url">
          </div>
          <div class="post-text">
            <p>{{ formatDate(post.sys.createdAt) }}</p>
            <h2>{{ post.fields.title }}</h2>
          </div>
        </nuxt-link>
      </div>
      <Aside/>
    </section>
  <Footer/>
  </div>
</template>

<script>
import client from '~/plugins/contentful';
import Header from '../components/Header';
import Footer from '../components/Footer';
import Aside from '../components/Aside';
export default {
  components : {
    Header,
    Footer,
    Aside,
  },
  asyncData({ params }) {
    return client
      .getEntries({
        content_type: 'post',
        order: '-sys.createdAt',
      })
      .then(entries => {
        return { posts: entries.items }
      })
      .catch(e => console.log(e))
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
.wrapper {
  background: #eee;
}
section.latest__posts {
  display: flex;
  max-width: 1200px;
  margin: 0 auto;
  .posts {
    width: percentage(850/1200);
    margin: 0 auto 0 0;
    a.post {
      display: flex;
      margin: 0 0 30px;
      padding: 10px;
      color: #111;
      text-decoration: none;
      background: #fff;
      box-shadow: 2px 2px 5px rgba(0,0,0,.2);
      .thumb {
        max-width: 180px;
        img {
          max-width: 100%;
          border: 1px solid #eee;
        }
      }
      .post-text {
        padding: 5px 20px 10px;
        h2 {
          font-size: 20px;
        }
      }
    }
  }
}
</style>
