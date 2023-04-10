<script lang="ts" setup>
const { t } = useLang()
</script>
<template>
  <div class="map h-180">
    <div
      class="map_header flex flex-row flex-nowrap justify-center items-center h-20"
    >
      <Anchor class="map_font mx-8">{{ t('footer.map.mapIsLand') }}</Anchor>
      <span>|</span>
      <Anchor class="map_font mx-8">{{ t('footer.map.Kowloon') }}</Anchor>
      <span>|</span>
      <Anchor class="map_font mx-8">{{ t('footer.map.Territories') }}</Anchor>
    </div>
    <div class="m-6">
      <div class="flex flex-row justify-center">
        <Anchor class="map_footer">{{ t('footer.map.YalanMong') }}</Anchor>
        <span>|</span>
        <Anchor class="map_footer">{{ t('footer.map.MongKok') }}</Anchor>
      </div>
      <div class="rectangle container mx-auto">
        <div>
          <iframe
            src="https://surl.amap.com/4MhMHbl1k449"
            width="600"
            height="450"
            style="border: 0"
            allowfullscreen=""
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade"
          ></iframe>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.map {
  background: #f2fcff;
}

.map_header {
  background: #aad4e5;
}

.map_font {
  font-family: 'ABeeZee';
  font-style: normal;
  font-weight: 400;
  font-size: 25px;
  line-height: 30px;
  /* identical to box height */

  display: flex;
  align-items: center;

  /* White */

  color: #ffffff;
}

.map_font:active {
  color: #3e5270;
}

.map_font:link {
  color: #3e5270;
}

.map_header > span {
  font-size: 40px;
  font-weight: 100;
  color: #ffffff;
}

.map_footer {
  font-family: 'ABeeZee';
  font-style: normal;
  font-weight: 400;
  font-size: 25px;
  line-height: 30px;
  display: flex;
  align-items: center;

  color: #a9a9a9;
}

.map_footer:active {
  color: #00a4ce;
}

.map_footer:link {
  color: #00a4ce;
}

.map_footer + span {
  font-size: 40px;
  font-weight: 200;
  color: #a9a9a9;
  margin: 0 2.8rem;
}

.rectangle {
  height: 493px;
  width: 884px;
  background: #ffffff;
}
</style>
