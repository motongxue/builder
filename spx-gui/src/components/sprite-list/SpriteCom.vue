<!--
 * @Author: Xu Ning
 * @Date: 2024-01-18 17:11:19
 * @LastEditors: Xu Ning
 * @LastEditTime: 2024-01-18 22:56:59
 * @FilePath: /spx-gui-front-private/src/components/sprite-list/SpriteCom.vue
 * @Description: 
-->
<template>
  <div :class="cardClassName">
    <div class="close-button">×</div>
    <n-image
      :width="imageWidth"
      :height="imageHeight"
      :src="props.asset.address"
      fallback-src="https://07akioni.oss-cn-beijing.aliyuncs.com/07akioni.jpeg"
    />
    {{ props.type === "bg" ? "" : props.asset.name }}
  </div>
</template>

<script setup lang="ts">
import { Asset } from "@/interface/library.ts";
import { defineProps, computed } from "vue";
import { NImage } from "naive-ui";
interface propType {
  type?: string;
  asset: Asset;
}
const props = defineProps<propType>();

const cardClassName = computed(() =>
  props.type === "bg" ? "bg-list-card" : "sprite-list-card"
);
const imageWidth = computed(() => (props.type === "bg" ? 40 : 75));
const imageHeight = computed(() => (props.type === "bg" ? 40 : 75));
</script>

<style scoped lang="scss">
@import "@/assets/theme.scss";

@mixin listCardBase {
  margin: 10px auto;
  border-radius: 20px;
  box-shadow: 0 0 5px $sprite-list-card-box-shadow;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  overflow: visible; // show x button
  cursor: pointer;

  .close-button {
    position: absolute;
    top: -5px;
    right: -10px;
    background-color: $sprite-list-card-close-button;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    color: $sprite-list-card-close-button-x;
    border: 2px solid $sprite-list-card-close-button-border;
    z-index: 10;
  }
}

.bg-list-card {
  @include listCardBase;
  width: 60px;
  height: 60px;

  .close-button {
    width: 15px;
    height: 15px;
    font-size: 20px;
  }
}

.sprite-list-card {
  @include listCardBase;
  width: 110px;
  height: 110px;

  .close-button {
    width: 30px;
    height: 30px;
    font-size: 40px;
  }
}
</style>
