<template>
  <aside>
    <Profile/>
    <Tag/>
    <Latest/>
  </aside>
</template>

<script>
import client from '~/plugins/contentful';
import Profile from '../components/Profile';
import Tag from '../components/Tag';
import Latest from '../components/Latest';
export default {
  components : {
    Profile,
    Tag,
    Latest,
  },
}
</script>

<style lang="scss">
  aside {
    width: percentage(300/1200);
  }
</style>
