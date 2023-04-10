<template>
  <div class="flex-1 w-full flex flex-col bg-blue-300 min-h-screen">
    <div class="min-h-full first_page">
      <div class="bg_peomi transform motion-safe:hover:scale-105">
        <img
          class="img transform motion-safe:hover:scale-105"
          src="https://static.cmereye.com/imgs/2023/04/949a53d691437ec7.png"
        />
        <text>兒童視光服務</text>
      </div>
      <div class="bg_peo transform motion-safe:hover:scale-105">
        <text>成人視光服務</text>
        <img
          class="img transform motion-safe:hover:scale-105"
          src="https://static.cmereye.com/imgs/2023/04/23a9931f7bb7b510.png"
        />
      </div>

      <div class="ba_bottom transform motion-safe:hover:scale-110">
        <img
          src="https://static.cmereye.com/imgs/2023/04/d0c98fe41950ca01.png"
        />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.first_page {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-around;
}

.bg_peomi,
.bg_peo {
  width: 260px;
  height: 70px;
  font-family: 'Noto Sans CJK TC';
  font-style: normal;
  font-weight: 700;
  font-size: 28px;
  line-height: 41px;
  box-sizing: border-box;

  display: flex;
  align-items: center;
}

.bg_peomi {
  background: #ffee54;
  border: 1.71498px solid #ffffff;
  border-radius: 46px;
  text-align: right;
  color: #00a4ce;

  position: absolute;
  top: 460px;
  left: 200px;
}

.bg_peo {
  background: #ffffff;
  opacity: 0.9;
  border: 1.58937px solid #00a4ce;
  border-radius: 52px;
  color: #00a4ce;

  position: absolute;
  top: 460px;
  right: 200px;
}

.bg_peo > text,
.bg_peomi > img {
  padding: 0 25px;
}

.img {
  display: inline-block;
}

.ba_bottom {
  position: absolute;
  left: 50.83%;
  right: 47.77%;
  bottom: 14.11%;
  top: 85.44%;
}
</style>
