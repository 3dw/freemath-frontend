<script lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { defineComponent, ref, onMounted } from 'vue'
import axios from 'axios'
export default defineComponent({
  setup() {
    const units = ref([])
    const global_current_unit = ref(null)
    const si = ref(false)
    onMounted(() => {
      axios.get('https://math.alearn.org.tw/api/units.json').then(response => {
        units.value = response.data
      })
    })
    return {
      units,
      global_current_unit,
      si
    }
  },
  methods: {
    setCurrentUnit(unit) {
      this.global_current_unit = unit
      console.log('設定單元:', unit)
    }
  }
})
</script>

<template>
  <nav class="ui fixed top menu">
    <RouterLink to="/" class="item">
      <i class="home icon"></i>
      <span>數學診療室</span>
    </RouterLink>
    <RouterLink to="/about" class="item">
      <i class="info icon"></i>
      <span>使用說明</span>
    </RouterLink>
  </nav>

  <div class="small-spacer"></div>

  <RouterView :units="units" :global_current_unit="global_current_unit" :si="si" @set-current-unit="setCurrentUnit" />
</template>

<style scoped>
.small-spacer {
  height: 50px;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
}

nav a.router-link-exact-active {
  color: #900 !important;
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

</style>
