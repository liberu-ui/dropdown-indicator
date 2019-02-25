<template>
    <span class="icon angle"
        :aria-hidden="!expanded">
        <fa icon="angle-down"/>
    </span>
</template>

<script>

import { library } from '@fortawesome/fontawesome-svg-core';
import { faAngleDown } from '@fortawesome/free-solid-svg-icons';

library.add(faAngleDown);

export default {
    model: {
        prop: 'collapsed',
        event: 'toggle',
    },

    props: {
        collapsed: {
            type: Boolean,
            default: true,
        },
    },

    data: v => ({
        expanded: !v.collapsed,
    }),

    watch: {
        collapsed(collapsed) {
            this.expanded = !collapsed;
        },
    },

    methods: {
        toggle() {
            this.expanded = !this.expanded;
            this.$emit('toggle', this.expanded);
        },
    },
};

</script>

<style lang="scss">
    .icon.angle[aria-hidden="true"] {
        transform: rotate(180deg);
    }

    .icon.angle {
        transition: transform .300s ease;
    }
</style>
