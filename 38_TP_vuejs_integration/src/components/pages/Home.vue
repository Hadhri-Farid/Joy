<template lang="html">
    <div class="wrap">
        <button
            id="up"
            @click="doScroll($event)"
            data-cible="#macible">
                <span>scroll down</span>
        </button>

        <div class="page">
            <h1>{{ title }}</h1>
            <pipo :content="contentPipo"></pipo>
            <pipo :content="warning"></pipo>
            <pipo :content="success"></pipo>
        </div>

        <button
            @click="doScroll($event)"
            data-cible="#up">
                <span>scroll up</span>
        </button>

        <div id="macible" class="page">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
        </div>
    </div>
</template>

<script>
import { eventBus } from "../../main";
import Pipo from "../shared/Pipo.vue";

export default {
    data() {
        return {
            contentPipo: "yo je suis le contenu de pipo et j'arrive du component Home",
            warning: "attention !!!",
            success: "great, u got it !!!",
            title: "Home"
        }
    },
    methods: {
        doScroll(e) {
            const sCSS = e.target.getAttribute("data-cible");
            const cible = this.$el.querySelector(sCSS);
            // console.log(e);
            // console.log(sCSS);
            // console.log(cible);
            smoothscroll(cible, 500);
        }
    },
    components: {
        Pipo
    },
    created() {

        eventBus.$on("dataDispatched", (message) => {
            console.log(message);
        });
    }
}
</script>

<style lang="scss" scoped>

button span {
    pointer-events: none;
}

</style>
