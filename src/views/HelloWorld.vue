<template>
  <h1>{{ msg }}</h1>
  <p>
    Recommended setup:
    <a href="https://code.visualstudio.com/" target="_blank">VSCode</a>
    +
    <a
      href="https://marketplace.visualstudio.com/items?itemName=octref.vetur"
      target="_blank"
      >Vetur</a
    >
  </p>
  <p>
    Make sure to use workspace version of TypeScript to get improved support via
    <a href="https://github.com/znck/vue-developer-experience" target="_blank"
      >@vuedx</a
    >.
  </p>
  <Button type="primary" @click="handleClick">count is: {{ count }}</Button>
  <Overlay :show="show" @click="show = false">
  </Overlay>
  <p>
    Edit <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue'
import { Button, Overlay } from 'vant'
export default defineComponent({
  name: 'HelloWorld',
  props: {
    msg: {
      type: String,
      required: true
    }
  },
  data () {
    return {
      show: false
    }
  },
  setup: () => {
    const count = ref(0)
    return { count }
  },
  methods: {
    handleClick() {
      this.show = true
    }
  },
  components: {
    Button,
    Overlay
  }
})
</script>
