<template>
  <view>
    <uni-popup ref="popup" :is-mask-click="false" background-color="#fff">
      <slot></slot>
    </uni-popup>
  </view>
</template>

<script setup lang="ts">
import { ref, defineProps, watch } from "vue";
const props = defineProps({
  show: {
    type: Boolean,
    default: false,
  },
});
const popup = ref<any>(null);

watch(() => props.show, (nv: boolean) => {
  console.log("nv", nv);
  if (nv) {
    popup.value?.open();
  } else {
    popup.value?.close();
  }
});
</script>

<style lang="scss" scoped>
.uni-popup {
    ::v-deep .uni-popup__wrapper {
        background: #FFFFFF !important;
        border-radius: 20rpx !important;
    }
}
</style>
