<template>
	<div class="footer">
        <p>Footer</p>
        <small v-if="isMounted">{{ currentTime }}</small>
    </div>
</template>

<script>
import { ref } from 'vue';

const TIME_INTERVAL = 1000;

export default {
    setup() {
        return {
            currentTime: ref(null),
            interval: ref(null),
            isMounted: ref(false),
        };
    },
    created() {
        this.currentTime = this.getCurrentTime();
    },
    mounted() {
        console.log('[Footer] mounted');
        this.isMounted = true;
        // update the time every second
        this.interval = setInterval(() => {
            this.currentTime = this.getCurrentTime()
        }, TIME_INTERVAL);
    },
    methods: {
        getCurrentTime() {
            return new Date().toLocaleTimeString();
        },
    },
};
</script>

<style>
.footer {
    background-color: lightgreen;
    text-align: center;
    padding: 3em;
}
</style>
