<template>
	<aside class="side">
        <p>Side</p>

        <Ad
            title="SSR Ad (Vue)"
            image="https://placekitten.com/400/200"
            :width="200"
            :height="100" />

        <Ad
            title="SSR Ad (Vue)"
            image="https://placekitten.com/600/600"
            :width="300"
            :height="300" />
    </aside>
</template>

<script>
import Ad from './Ad.vue';

export default {
    components: {
        Ad,
    }
};
</script>

<style>
.side {
    background-color: lightcoral;
    text-align: center;
}
</style>
