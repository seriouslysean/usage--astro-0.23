<template>
	<div class="nav">
        <ul>
            <li v-for="(link, idx) in links" :key="`${idx}-${link.href}`">
                <a
                    :href="link.href"
                    :title="link.title"
                    @click.prevent="handleLinkClick($event, link)">

                    {{ link.text }}
                </a>
            </li>
        </ul>

        <div class="nav__clicked">
            {{ currentLinkTitle }}
        </div>

        <p>These links will notify which url the link would go to when hydrated and js is active. If Javascript is disabled they will go directly to an external url when javascript is off.</p>
    </div>
</template>

<script>
import { ref} from 'vue';

export default {
	setup() {
		const linkTitle = ref(null);
		return {
			linkTitle,
		};
	},
    created() {
        this.links = [
            {
                href: 'https://www.urbn.com',
                title: 'URBN',
                text: 'URBN',
            },
            {
                href: 'https://www.anthropologie.com',
                title: 'AN',
                text: 'Anthropologie',
            },
            {
                href: 'https://www.freepeople.com',
                title: 'FP',
                text: 'Free People',
            },
            {
                href: 'https://www.urbanoutfitters.com',
                title: 'UO',
                text: 'Urban Outfitters',
            },
        ];
    },
    computed: {
        currentLinkTitle() {
            return this.linkTitle || 'Title';
        },
    },
    methods: {
        handleLinkClick(event, link) {
            this.linkTitle = link.title;
        },
    },
};
</script>

<style>
.nav {
    background-color: lightcoral;
    padding: 1em;
}

.nav__clicked {
    margin: 1em 0;
    background: rgba(0, 0, 0, 0.25);
    color: white;
    padding: 1em;
    text-align: center;
}

.nav p {
    font-size: 0.75em;
}
</style>
