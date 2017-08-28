<template>
    <section class="page">
        <h1>my @dmin</h1>
        <testimony-form></testimony-form>
        <testimony-tabler></testimony-tabler>
    </section>
</template>
<script>
import TestimonyForm from "../testimony/Form.vue";
import TestimonyTabler from "../testimony/Tabler.vue";

export default {
    components: {
        TestimonyForm,
        TestimonyTabler
    },
    data() {
        return {

        }
    },
    methods: {

    }
}
</script>
<style scoped>

</style>
