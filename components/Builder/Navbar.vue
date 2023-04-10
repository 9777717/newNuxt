<script lang="ts" setup>
import { AppConfigInput } from '@nuxt/schema'

// state
const app = useAppConfig() as AppConfigInput
const navbar = ref(null)
const showDrawer = useState<boolean>('navbar.showDrawer', () => false)
const showOptions = useState<boolean>('navbar.showOptions', () => false)

// lifecycle
let timer: NodeJS.Timer
onMounted(() => {
  if (!navbar.value) return

  // scroll
  const { onScroll } = useSticky(navbar.value, 0)
  setTimeout(() => onScroll(), 50)

  // on show on mobile
  setInterval(() => {
    // must in mobile
    const minW = 1024
    if (window.innerWidth < minW) {
      updateDrawerOptions()
    }
  }, 100)
})
onBeforeUnmount(() => {
  if (timer) clearInterval(timer)
})

// methods
const updateDrawerOptions = () => {
  // drawer
  if (showDrawer.value || showOptions.value) {
    document.body.classList.add('overflow-hidden')
  } else {
    document.body.classList.remove('overflow-hidden')
  }
}
const toggleDrawer = () => (showDrawer.value = !showDrawer.value)
const toggleOptions = (show?: boolean) => {
  if (show) {
    showOptions.value = show
  } else {
    showOptions.value = !showOptions.value
  }
}
</script>

<template>
  <div ref="navbar" class="bg-bule flex flex-row flex-nowrap">
    <div class="pl-12 py-4">
      <NuxtLink tag="a" :to="{ name: 'index' }">
        <img
          class="logo_link"
          src="https://static.cmereye.com/imgs/2023/04/ce697599637c01b0.png"
        />
      </NuxtLink>
    </div>
    <div class="py-4">
      <img
        class="adv"
        src="https://static.cmereye.com/imgs/2023/04/3921bef7289ff4d9.png"
      />
    </div>
    <div class="">
      <slot name="menu" />
    </div>
  </div>
</template>
<style lang="scss" scoped>
.slide-fade-from-up-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-from-up-leave-active {
  transition: all 0.3s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-from-up-enter-from,
.slide-fade-from-up-leave-to {
  transform: translateY(-20px);
  opacity: 0;
}

a.router-link-active {
  font-weight: bold;
}

a.router-link-exact-active {
  color: theme('colors.slate.900');
}

html.dark {
  a.router-link-exact-active {
    color: theme('colors.white');
  }
}
</style>

<style lang="scss" scoped>
.bg-bule {
  background-color: rgba(0, 164, 206, 0.9);
  justify-content: space-between;
}

.logo_link {
  width: 147px;
  height: 54px;
}
.adv {
  width: 187px;
  height: 59px;
}
</style>
