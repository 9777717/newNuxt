<script lang="ts" setup>
import { AppConfigInput } from '@nuxt/schema'

export interface IMenuItem {
  type: 'link' | 'button'
  text: string
  href?: any
  route?: any
}

const { t } = useLang()
const app = useAppConfig() as AppConfigInput
const menus = computed((): IMenuItem[] => [
  { type: 'link', text: t('pages.blank.nav'), route: { name: 'blank' } },
  { type: 'link', text: t('pages.test.nav'), route: { name: 'test' } },
  { type: 'link', text: t('pages.setting.nav'), route: { name: 'setting' } },
  // {
  //   type: 'button',
  //   text: t('pages.dashboard.nav'),
  //   route: { name: 'dashboard' },
  // },
])
</script>

<template>
  <BuilderNavbar>
    <template #menu>
      <div class="right_text">
        <div class="text space-x-4 flex items-center">
          <div class="text_whats">
            <img
              src="https://static.cmereye.com/imgs/2023/04/bbd64119a071aecd.png"
              alt="WhatsApp"
            />
            <text class="text-base font-bold md:text-lg p-2">WhatsApp</text>
            <!-- class="hover:no-underline hover:text-slate-900 hover:dark:text-white capitalize" -->
          </div>
          <div class="text_tel p-4">
            <img
              src="https://static.cmereye.com/imgs/2023/04/56577123ca0c1773.png"
              alt="電話查詢"
            />
            <text class="text-base font-bold md:text-lg p-2">{{
              t('pages.index.inquire')
            }}</text>
          </div>
        </div>
        <div class="img p-4 mt-6">
          <img
            src="https://static.cmereye.com/imgs/2023/04/92e29b10f3a22ee5.png"
          />
        </div>
        <!-- <LanguageSwitcher /> -->
        <!-- <ThemeSwitcher /> -->
      </div>
      <!-- <div class="flex space-x-4 border-l ml-6 pl-6 border-gray-900/10 dark:border-gray-50/[0.2]"> -->
      <!--- 语言翻译  --->
      <!-- <LanguageSwitcher /> -->
      <!--- 主题 --->
      <!-- <ThemeSwitcher /> -->
      <!-- </div> -->
    </template>
  </BuilderNavbar>
</template>

<style lang="scss" scoped>
.right_text {
  color: white;
  display: flex;
  height: 100%;
}

.right_text > div {
  display: flex;
  align-items: stretch;
}

.text > div {
  display: flex;
  align-items: center;
  flex-direction: row;
}

//
.text_tel {
  background: #ffee54;

  text {
    color: #00a4ce;
  }
}

.right_text {
  .img {
    img {
      width: 22px;
      height: 20px;
    }
  }
}
</style>
