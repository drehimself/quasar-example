<template>
  <q-page padding>
    <div class="row q-gutter-xs">
      <div class="col">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Inventore alias vel obcaecati repudiandae similique possimus delectus quam hic nam? Hic nihil, obcaecati consectetur ullam incidunt cupiditate tempora corrupti. Mollitia, earum.
        <div>
          <q-btn color="teal" @click="showLoading" label="Show Loading" />
          <q-btn color="primary" label="Primary" @click="handleClick" />
          <q-input outlined v-model="myInput" label="Outlined" />
        </div>
        <p v-for="n in 50" :key="n">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugit nihil praesentium molestias a adipisci, dolore vitae odit, quidem consequatur optio voluptates asperiores pariatur eos numquam rerum delectus commodi perferendis voluptate?
          </p>

          <!-- place QPageScroller at end of page -->
          <q-page-scroller position="bottom-right" :scroll-offset="150" :offset="[18, 18]">
            <q-btn fab icon="keyboard_arrow_up" color="accent" />
          </q-page-scroller>
      </div>
      <div class="col">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Inventore alias vel obcaecati repudiandae similique possimus delectus quam hic nam? Hic nihil, obcaecati consectetur ullam incidunt cupiditate tempora corrupti. Mollitia, earum.
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      myInput: ''
    }
  },
  methods: {
    handleClick () {
      this.myInput = 'clicked'
    },
    showLoading () {
      this.$q.loading.show({
        message: 'Some important process is in progress. Hang on...'
      })

      // hiding in 3s
      this.timer = setTimeout(() => {
        this.$q.loading.hide()
        this.timer = void 0
      }, 3000)
    }
  }
}
</script>
