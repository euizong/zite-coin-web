<template>
  <div class="foo">
    <p>Test!234</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      a: 0
    }
  },

  metaInfo: {
    title: 'Vue SSR Boilerplate',
    meta: [
      { vmid: 'description', name: 'description', content: 'Vue SSR Boilerplate' }
    ]
  },

  prefetch() {
    return Promise.resolve({
      a: 123
    })
  },

  // will be called on server side. check your console
  created() {
    console.log(this.a) //eslint-disable-line
  },

  // won't run on server side
  beforeMount() {
    console.log(this.a) //eslint-disable-line
  }
}
</script>
