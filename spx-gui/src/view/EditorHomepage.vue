<!--
 * @Author: Yao xinyue kother@qq.com
 * @Date: 2024-01-12 17:30:39
 * @LastEditors: Xu Ning
 * @LastEditTime: 2024-01-17 22:59:45
 * @FilePath: /spx-gui-front-private/src/view/EditorHomepage.vue
 * @Description:
-->
<template>
  <n-layout has-sider style="height: 100%;">
    <n-layout style="width: 60%;" collapsible>
      <!-- S Component SpxEditor -->
      <SpxEditor></SpxEditor>
      <!-- E Component SpxEditor -->
    </n-layout>
    <n-layout style="width: 40%;">
      <n-layout-content>
        <!-- S Component SpxStage -->
        <SpxStage />
        <!-- E Component SpxStage -->
        <!-- S Component assetLibrary -->
        <SpriteList />
        <!-- E Component assetLibrary -->
      </n-layout-content>
    </n-layout>
  </n-layout>
</template>

<script setup lang="ts">
import SpxEditor from "@/components/spx-editor/SpxEditor.vue";
import SpxStage from "@/components/spx-stage/SpxStage.vue";
import SpriteList from "@/components/sprite-list/SpriteList.vue";
import { NLayout, NLayoutContent } from "naive-ui";

</script>

<style scoped>

</style>
