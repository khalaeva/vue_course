<script setup>
    import { reactive, ref } from "vue";

    const counter = ref(0);

    function counterHandler(event) {
        console.log();
    }
</script>

<template>
    <button @click="counter++">counter {{ counter }}</button>
</template>

<style lang="scss" scoped></style>