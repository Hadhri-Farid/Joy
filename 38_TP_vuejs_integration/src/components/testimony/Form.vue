<template>
    <form class="form">
        je suis le form de testimony

        <button class="btn">témoigner</button>
    </form>
</template>
<script>
export default {
    data() {
        return {

        }
    },
    methods: {
        submitForm(e) {
            console.log(e);
        }
    }
}
</script>
<style scoped>
.btn {
    background: white;
    border-radius: .3rem;
    border: 1px solid silver;
}
.btn:hover {
    color: white;
    background: forestgreen;
}

</style>
