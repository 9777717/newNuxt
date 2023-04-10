<script lang="ts" setup>
import { AppConfigInput } from '@nuxt/schema'
import p from './../../package.json'
const currentYear: number = new Date().getFullYear()
const { t } = useLang()
const app = useAppConfig() as AppConfigInput
</script>

<template>
  <PageMapMsg />
  <footer
    class="flex flex-col px-61 py-25 border-t lg:border-gray-900/10 dark:border-gray-50/[0.2]"
  >
    <section class="px-4 lg:px-8 flex-1 flex w-full space-x-20">
      <div
        class="flex flex-nowrap justify-between w-full py-4 text-center md:text-left footer_top"
      >
        <div>
          <div>{{ t('footer.aboutUs.aboutUs') }}</div>
          <ul>
            <li>{{ t('footer.aboutUs.Hema') }}</li>
          </ul>
        </div>
        <div>
          <div>{{ t('footer.Exclusive.Exclusive') }}</div>
        </div>
        <div>
          <div>{{ t('footer.Myopia.Myopia') }}</div>
          <ul>
            <li>{{ t('footer.Myopia.Orthokeratoplasty') }}</li>
            <li>{{ t('footer.Myopia.controlOptics') }}</li>
            <li>{{ t('footer.Myopia.MiSight') }}</li>
          </ul>
        </div>
        <div>
          <div>{{ t('footer.Optician.Optician') }}</div>
          <ul>
            <li>{{ t('footer.Optician.Progressive') }}</li>
            <li>{{ t('footer.Optician.Presbyopia') }}</li>
            <li>{{ t('footer.Optician.HardLenses') }}</li>
          </ul>
        </div>
        <div>
          <div>{{ t('footer.optometry.optometry') }}</div>
          <ul>
            <li>{{ t('footer.optometry.Comprehensive') }}</li>
            <li>{{ t('footer.optometry.MyopicControlTest') }}</li>
            <li>{{ t('footer.optometry.lensFitting') }}</li>
            <li>{{ t('footer.optometry.Glaucoma') }}</li>
          </ul>
        </div>
        <div>
          <div>{{ t('footer.Service.Service') }}</div>
          <ul>
            <li>{{ t('footer.Service.ServicesList') }}</li>
            <li>{{ t('footer.Service.ServicesCharge') }}</li>
            <li>{{ t('footer.Service.VoucherScheme') }}</li>
          </ul>
        </div>
        <div>
          <div>{{ t('footer.sharing.sharing') }}</div>
        </div>
        <div>
          <div>{{ t('footer.EyeKnowledge.EyeKnowledge') }}</div>
          <ul>
            <li>{{ t('footer.EyeKnowledge.LittleEye') }}</li>
            <li>{{ t('footer.EyeKnowledge.childrenEye') }}</li>
            <li>{{ t('footer.EyeKnowledge.CommonEye') }}</li>
          </ul>
        </div>
        <div>
          <div>{{ t('footer.ContactUs.ContactUs') }}</div>
          <ul>
            <li class="flex flex-nowrap justify-between mt-3">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="1em"
                height="1em"
                viewBox="0 0 32 32"
              >
                <path
                  fill="#888888"
                  d="M32 16c0-8.839-7.167-16-16-16C7.161 0 0 7.161 0 16c0 7.984 5.849 14.604 13.5 15.803V20.626H9.437v-4.625H13.5v-3.527c0-4.009 2.385-6.223 6.041-6.223c1.751 0 3.584.312 3.584.312V10.5h-2.021c-1.984 0-2.604 1.235-2.604 2.5v3h4.437l-.713 4.625H18.5v11.177C26.145 30.603 32 23.983 32 15.999z"
                ></path>
              </svg>

              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="1em"
                height="1em"
                viewBox="0 0 32 32"
              >
                <path
                  fill="#888888"
                  d="M16 0c-4.349 0-4.891.021-6.593.093c-1.709.084-2.865.349-3.885.745a7.847 7.847 0 0 0-2.833 1.849A7.757 7.757 0 0 0 .84 5.52C.444 6.54.179 7.696.095 9.405c-.077 1.703-.093 2.244-.093 6.593s.021 4.891.093 6.593c.084 1.704.349 2.865.745 3.885a7.847 7.847 0 0 0 1.849 2.833a7.757 7.757 0 0 0 2.833 1.849c1.02.391 2.181.661 3.885.745c1.703.077 2.244.093 6.593.093s4.891-.021 6.593-.093c1.704-.084 2.865-.355 3.885-.745a7.847 7.847 0 0 0 2.833-1.849a7.716 7.716 0 0 0 1.849-2.833c.391-1.02.661-2.181.745-3.885c.077-1.703.093-2.244.093-6.593s-.021-4.891-.093-6.593c-.084-1.704-.355-2.871-.745-3.885a7.847 7.847 0 0 0-1.849-2.833A7.716 7.716 0 0 0 26.478.838c-1.02-.396-2.181-.661-3.885-.745C20.89.016 20.349 0 16 0zm0 2.88c4.271 0 4.781.021 6.469.093c1.557.073 2.405.333 2.968.553a4.989 4.989 0 0 1 1.844 1.197a4.931 4.931 0 0 1 1.192 1.839c.22.563.48 1.411.553 2.968c.072 1.688.093 2.199.093 6.469s-.021 4.781-.099 6.469c-.084 1.557-.344 2.405-.563 2.968c-.303.751-.641 1.276-1.199 1.844a5.048 5.048 0 0 1-1.844 1.192c-.556.22-1.416.48-2.979.553c-1.697.072-2.197.093-6.479.093s-4.781-.021-6.48-.099c-1.557-.084-2.416-.344-2.979-.563c-.76-.303-1.281-.641-1.839-1.199c-.563-.563-.921-1.099-1.197-1.844c-.224-.556-.48-1.416-.563-2.979c-.057-1.677-.084-2.197-.084-6.459c0-4.26.027-4.781.084-6.479c.083-1.563.339-2.421.563-2.979c.276-.761.635-1.281 1.197-1.844c.557-.557 1.079-.917 1.839-1.199c.563-.219 1.401-.479 2.964-.557c1.697-.061 2.197-.083 6.473-.083zm0 4.907A8.21 8.21 0 0 0 7.787 16A8.21 8.21 0 0 0 16 24.213A8.21 8.21 0 0 0 24.213 16A8.21 8.21 0 0 0 16 7.787zm0 13.546c-2.948 0-5.333-2.385-5.333-5.333s2.385-5.333 5.333-5.333c2.948 0 5.333 2.385 5.333 5.333S18.948 21.333 16 21.333zM26.464 7.459a1.923 1.923 0 0 1-1.923 1.921a1.919 1.919 0 1 1 0-3.838c1.057 0 1.923.86 1.923 1.917z"
                ></path>
              </svg>

              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="1em"
                height="1em"
                viewBox="0 0 32 32"
              >
                <path
                  fill="#888888"
                  d="M31.328 8.271a4.006 4.006 0 0 0-2.787-2.781c-2.495-.667-12.525-.667-12.525-.667S6.005 4.807 3.484 5.49A4.005 4.005 0 0 0 .703 8.271a41.574 41.574 0 0 0-.697 7.745a42.136 42.136 0 0 0 .697 7.708a4.022 4.022 0 0 0 2.781 2.787c2.495.667 12.532.667 12.532.667s10.005 0 12.525-.667a4.023 4.023 0 0 0 2.787-2.787c.459-2.541.683-5.125.667-7.708c.016-2.6-.203-5.188-.667-7.745zM12.812 20.803v-9.595l8.349 4.808z"
                ></path>
              </svg>
            </li>
          </ul>
        </div>
      </div>
    </section>
    <section class="pt-1 px-4 lg:px-8 flex-1 flex w-full space-x-20">
      <div
        class="flex flex-nowrap justify-between items-center w-full py-4 text-center md:text-left"
      >
        <div class="flex flex-row">
          <div class="flex mr-18">
            <Anchor href="https://www.baidu.com">{{
              t('footer.copyright.conditions')
            }}</Anchor>
          </div>
          <div class="flex items-center">
            <svg
              t="1680847272773"
              class="icon"
              viewBox="0 0 1024 1024"
              version="1.1"
              xmlns="http://www.w3.org/2000/svg"
              p-id="2593"
              width="20"
              height="20"
            >
              <path
                d="M507.469576 183.699394c-188.509091 0-341.333333 152.824242-341.333334 341.333333s152.824242 341.333333 341.333334 341.333334 341.333333-152.824242 341.333333-341.333334-152.824242-341.333333-341.333333-341.333333z m-403.39394 341.333333c0-222.797576 180.596364-403.393939 403.39394-403.393939s403.393939 180.596364 403.393939 403.393939-180.596364 403.393939-403.393939 403.39394-403.393939-180.596364-403.39394-403.39394z"
                fill="#303133"
                p-id="2594"
              ></path>
              <path
                d="M544.488727 406.528a124.121212 124.121212 0 1 0 62.277818 193.008485 31.030303 31.030303 0 0 1 49.648485 37.236363 186.181818 186.181818 0 1 1 0-223.511272 31.030303 31.030303 0 1 1-49.648485 37.236363 124.121212 124.121212 0 0 0-62.277818-43.969939z"
                fill="#303133"
                p-id="2595"
              ></path>
            </svg>
            {{ currentYear }} {{ t('footer.copyright.manage') }}
            <div class="flex ml-2">
              {{ t('footer.copyright.copyright') }} |
              {{ t('footer.copyright.Privacy') }}
            </div>
          </div>
        </div>
        <div>
          <img
            src="https://static.cmereye.com/imgs/2023/04/1af3d50e7c4642fc.png"
          />
        </div>
      </div>
    </section>
  </footer>
</template>

<style lang="scss" scoped>
.footer_top > div > div {
  font-family: 'Noto Sans CJK TC';
  font-style: normal;
  font-weight: 700;
  font-size: 24px;
  line-height: 36px;
  /* identical to box height */

  letter-spacing: 0.1em;

  /* Turquoise */

  color: #00a4ce;
}
.footer_top > div > ul > li {
  font-family: 'ABeeZee';
  font-style: normal;
  font-weight: 400;
  font-size: 20px;
  line-height: 44px;
  /* identical to box height, or 218% */

  /* Dark Grey */

  color: #3e5270;
}
</style>
