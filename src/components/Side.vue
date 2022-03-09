<template>
	<aside class="side">
        <p>Side</p>

        <Ad
            title="SSR Ad (Vue)"
            image="https://placekitten.com/200/100"
            :width="200"
            :height="100" />

        <Ad
            title="SSR Ad (Vue)"
            image="https://placekitten.com/300/100"
            :width="300"
            :height="100" />
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
