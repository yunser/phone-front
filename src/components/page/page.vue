<template>
    <ui-page :title="title || page.title" ref="page">
        <div slot="drawer">
            <div class="header">
                <img class="logo" src="/static/img/life.svg">
            </div>
            <ui-list @itemClick="toggle()">
                <ui-list-item title="首页" href="https://life.yunser.com/">
                    <ui-icon slot="left" value="grade"/>
                </ui-list-item>
                <!-- <ui-list-item title="手机号码归属地查询" to="/">
                    <ui-icon slot="left" value="grade"/>
                </ui-list-item>
                <ui-list-item title="常用电话号码" to="/common">
                    <ui-icon slot="left" value="grade"/>
                </ui-list-item> -->
                <!-- <ui-list-item title="关于" to="/about">
                    <ui-icon slot="left" value="grade"/>
                </ui-list-item> -->
            </ui-list>
        </div>
        <slot></slot>
    </ui-page>
</template>

<script>
    export default {
        data() {
            return {
                open: false,
                docked: true
            }
        },
        props: {
            title: {
                type: String,
                default: ''
            },
            name: {
                type: String,
                default: 'default'
            },
            page: {
                type: Object,
                default: function () {
                    return {
                        title: '云设'
                    }
                }
            },
            backable: {
                type: Boolean,
                default: false
            }
        },
        methods: {
            toggle() {
                console.log(this.$refs.page)
            }
        }
    }
</script>

<style lang="scss" scoped>
.header {
    padding: 40px 0;
    border-bottom: 1px solid rgba(0, 0, 0, 0.12);
}
.logo {
    display: block;
    width: 80px;
    margin: 0 auto;
}
.ui-position-bottom {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
}
</style>
