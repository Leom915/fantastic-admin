<template>
    <footer class="copyright">
        Copyright © {{ $store.state.global.copyrightDates }}
        <!-- eslint-disable-next-line vue/require-component-is -->
        <component v-bind="linkProps()">{{ $store.state.global.copyrightCompany }}</component>
    </footer>
</template>

<script>
export default {
    name: 'Copyright',
    methods: {
        linkProps() {
            if (this.$store.state.global.copyrightWebsite) {
                return {
                    is: 'a',
                    href: this.$store.state.global.copyrightWebsite,
                    target: '_blank',
                    rel: 'noopener'
                }
            } else {
                return {
                    is: 'span'
                }
            }
        }
    }
}
</script>

<style lang="scss" scoped>
footer {
    margin: 40px 0 20px 0;
    line-height: 20px;
    text-align: center;
    color: #808695;
    font-size: 14px;
    a {
        text-decoration: none;
        color: #808695;
        &:hover {
            color: #3d4047;
        }
    }
}
</style>
