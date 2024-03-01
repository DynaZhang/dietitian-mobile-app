<template>
    <view class="toast-wrapper" :style="toastStyle">
        <view class="toast-content">
            <view v-if="props.type" class="toast-content__icon">
                <cover-image :src="typeIcon"></cover-image>
            </view>
            <view class="toast-content__text">{{props.text}}</view>
        </view>
    </view>
</template>

<script setup lang="ts">
import { ref, defineProps, computed, onMounted } from 'vue'
import tipsIcon from '../../static/icons/tips.png';
const props = defineProps({
    type: {
        type: String,
        default: ''
    },
    text: {
        type: String,
        default: ''
    },
    position: {
        type: Object,
        default() {
            return {
                top: 0,
                left: 0
            }
        }
    },
    duration: {
        type: Number,
        default: 3000
    }
});
const emits = defineEmits(['close']);
const toastStyle = computed(() => {
    return {
        top: `${props.position.top}rpx`,
        left: `${props.position.left}rpx`
    }
});
const typeIcon = computed(() => {
    const iconMap: {[key: string]: any} = {
        info: tipsIcon
    };
    return props.type ? iconMap[props.type] : '';
})

onMounted(() => {
    props.duration > 0 && setTimeout(() => {
        emits('close');
    } , props.duration);
})

</script>

<style lang="scss" scoped>
.toast-wrapper {
    position: fixed;
    width: 499rpx;
    height: 104rpx;
    background: rgba(0,0,0,0.59);
    border-radius: 8rpx;
    z-index: 9999;
    .toast-content {
        width: 100%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        &__icon {
            width: 32rpx;
            height: 32rpx;
        }
        &__text {
            font-weight: 500;
            font-size: 28rpx;
            color: #FFFFFF;
            line-height: 104rpx;
            letter-spacing: 3px;
            text-align: left;
            font-style: normal;
        }
    }
}
</style>
