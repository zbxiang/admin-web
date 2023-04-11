<template>
  <ConfigProvider :locale="getAntdLocale">
    <AppProvider>
      <RouterView />
    </AppProvider>
  </ConfigProvider>
</template>

<script lang="ts" setup>
import { ConfigProvider } from "ant-design-vue";
import { AppProvider } from "/@/components/Application";
import { useTitle } from "/@/common/hooks/web/useTitle";
import { useLocale } from "/@/common/locales/useLocale";

import "dayjs/locale/zh-cn";
// support Multi-language
const { getAntdLocale } = useLocale();

// Listening to page changes and dynamically changing site titles
useTitle();
</script>
