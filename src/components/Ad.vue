<template>
	<div
        class="ad"
        :style="{
            'background-image': `url(${image})`,
            'padding-top': paddingTop,
        }">

        <p>{{ title }}</p>
    </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            required: true,
        },
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
    mounted() {
        console.log('[AD] mounted', this.title);
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
