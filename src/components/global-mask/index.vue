<!--
  global mask 组件 提供全局遮罩,全局只能存在一份拷贝
  @param {String} appendClass 自定义class
  @param {Object} appendStyle 自定义Style对象
-->
<template>
    <div :class="['vc-global-mask', {'vc-global-mask-hidden': !isShow}, appendClass]" :style="appendStyle"></div>
</template>
<script>
    import {componentBaseParamConfig} from '../base-config';

    export default {
        props: Object.assign({}, componentBaseParamConfig, {
            isShow: false
        }),

        methods: {
            show() {
                this.isShow = true;
            },

            hide() {
                this.isShow = false;
            }
        },
        watch: {
            isShow(val) {
                val ? this.show() : this.hide();
            }
        }
    }

</script>

<style lang="sass">
    @import "style.scss";
</style>