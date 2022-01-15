<template>
  <div ref="navbar" class="
    top-0 z-40 w-full backdrop-blur flex-none
    ransition-colors duration-500 lg:z-50
    border-b border-gray-900/10 dark:border-gray-50/[0.2]
    supports-backdrop-blur:bg-white/60 bg-white/[0.7] dark:bg-slate-900/[0.7]
    "
  >
    <div class="max-w-8xl mx-auto">
      <div class="py-4 lg:px-8 mx-4 lg:mx-0">
        <div class="relative flex items-center">
          <!-- drawer:toggle -->
          <div v-if="$slots['drawer']" class="md:hidden">
            <button class="flex items-center focus:outline-none py-1 px-2" @click="toggleDrawer()">
              <span class="text-gray-600 dark:text-gray-300 text-xl">
                <IconUil:bars v-if="!showDrawer" />
                <IconUil:times v-else />
              </span>
            </button>
          </div>
          <!-- title -->
          <NuxtLink tag="a" class="mr-3 flex-none overflow-hidden md:w-auto font-bold text-gray-900 dark:text-gray-200" :to="{ name: 'index' }">
            <span class="sr-only">home</span>
            <span class="flex items-center">
              <IconSimpleIcons:nuxtdotjs class="inline-block mr-2 text-xl text-green-600" />
              {{ app.name }}
            </span>
          </NuxtLink>
          <!-- menu -->
          <slot name="menu" />
          <!-- options:toggle -->
          <div v-if="$slots['options']" class="flex-1 flex justify-end md:hidden">
            <button class="flex items-center focus:outline-none py-1 px-2" @click="toggleOptions()">
              <span class="text-gray-600 dark:text-gray-300 text-sm">
                <icon-fa-solid:ellipsis-v />
              </span>
            </button>
          </div>
        </div>
      </div>
    </div>
    <ClientOnly>
      <Teleport to="#app-after">
        <!-- drawer -->
        <Transition name="slide-fade-from-up" mode="out-in">
          <div v-if="showDrawer && $slots['drawer']" class="fixed md:hidden bg-gray-100 dark:bg-slate-800 pt-16 top-0 left-0 w-screen h-screen z-30">
            <div class="px-4 py-2 relative">
              <slot name="drawer" :toggleDrawer="toggleDrawer" />
            </div>
          </div>
        </Transition>

        <!-- options -->
        <div v-if="showOptions && $slots['options']">
          <slot name="options" :toggleOptions="toggleOptions" />
        </div>
      </Teleport>
    </ClientOnly>
  </div>
</template>

<script lang="ts">
import { IApp } from "~/utils/app"
import {
  Dialog,
  DialogOverlay,
  DialogTitle,
  DialogDescription,
} from "@headlessui/vue";

export default defineComponent({
  components: {
    Dialog,
    DialogOverlay,
    DialogTitle,
    DialogDescription,
  },
  setup() {
    const app = useState<IApp>('app')
    const navbar = ref(null)
    const showDrawer = useState<boolean>('navbar.showDrawer', () => false)
    const showOptions = useState<boolean>('navbar.showOptions', () => false)

    onMounted(() => {
      const { onScroll } = stickyOnScroll(navbar.value as HTMLElement, 0)
      setTimeout(() => onScroll(), 50)
    })
    
    const toggleDrawer = () => showDrawer.value = !showDrawer.value
    const toggleOptions = (show?: boolean) => {
      if (show) {
        showOptions.value = show
      } else {
        showOptions.value = !showOptions.value
      }
    }

    return {
      app,
      navbar,
      showOptions,
      showDrawer,
      toggleDrawer,
      toggleOptions,
    }
  }
})

function stickyOnScroll(el: HTMLElement, offset: number) {
  const onScroll = () => {
    const scrollTop = window.pageYOffset || document.documentElement.scrollTop
    if (scrollTop > offset) {
      el.classList.add('sticky')
    } else {
      el.classList.remove('sticky')
    }
  }

  // lifecycle hooks
  window.addEventListener('scroll', onScroll)
  onUnmounted(() => {
    window.removeEventListener('scroll', onScroll)
  })

  return {
    onScroll,
  }
}
</script>

<style lang="scss">
.slide-fade-from-up-enter-active {
  transition: all .3s ease-out;
}
.slide-fade-from-up-leave-active {
  transition: all .3s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-from-up-enter-from,
.slide-fade-from-up-leave-to {
  transform: translateY(-20px);
  opacity: 0;
}
</style>