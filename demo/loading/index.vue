<template>
    <div>
        <v-button type="primary" @click.native="showLoading('Global')">全局loading</v-button>
        <v-button type="primary" @click.native="showLoading('Part')">局部loading</v-button>

        <v-loading :is-show="showGlobalLoading" :is-global="true" :content="'加载中..'"></v-loading>
        <v-loading :is-show="showPartLoading" :size="'small'"></v-loading>

        <a class="demo-link" href="../components/loading.html">组件连接</a>
    </div>
</template>

<script>
    import vLoading from '../../src/components/loading';
    import vButton from '../../src/components/button';

    export default {
        components: {
            vLoading,
            vButton
        },
        data() {
            return {
                showGlobalLoading: false,
                showPartLoading: false,
            }
        },
        methods: {
            showLoading(value) {
                var _this = this;

                _this['show' + value + 'Loading'] = true;

                setTimeout(function() {
                    _this['show' + value + 'Loading'] = false;
                }, 2000);
            }
        },
    }
</script>