<template>
    <span class="icon angle"
        :aria-hidden="!open">
        <fa icon="angle-down"/>
    </span>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core';
import { faAngleDown } from '@fortawesome/free-solid-svg-icons';

library.add(faAngleDown);

export default {
    name: 'DropdownIndicator',

    props: {
        open: {
            type: Boolean,
            default: false,
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
