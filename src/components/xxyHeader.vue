<template>

    <div class="xxyHeader">
        
        <wxc-minibar :title="title"
                   background-color="#009ff0"
                   text-color="#FFFFFF"
                   :right-text="rightTex"
                   :left-text="leftTex"
                   left-button=""
                   @wxcMinibarLeftButtonClicked="minibarLeftButtonClick"
                   @wxcMinibarRightButtonClicked="minibarRightButtonClick"></wxc-minibar>

    </div>

</template>

<style scoped>

</style>

<script>
    import { WxcMinibar } from 'weex-ui';
    const modal = weex.requireModule('modal');
    export default{
        props:[
            "title","leftTex","rightTex"
        ],
        components: { WxcMinibar },
        methods: {
            minibarLeftButtonClick () {
            },
            minibarRightButtonClick () {
                modal.toast({ 'message': 'click rightButton!', 'duration': 1 });
            }
        }

    }

</script>