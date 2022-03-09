<template>
	<div
        class="ad"
        :style="{
            'background-image': `url(${image})`,
            'padding-top': paddingTop,
        }">

        <p>Advertising</p>
    </div>
</template>

<script>
export default {
    props: {
        image: {
            type: String,
            required: true,
        },
        width: {
            type: Number,
            required: true,
        },
        height: {
            type: Number,
            required: true,
        },
    },
    computed: {
        paddingTop() {
            return `${(this.height / this.width) * 100}%`;
        },
    },
};
</script>

<style>
/* Styles in index.astro so both Vue ad and astro ad can use them */
</style>
