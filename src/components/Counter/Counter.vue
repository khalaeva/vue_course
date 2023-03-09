<script setup>
    import { reactive, ref, watchEffect, watch } from "vue";

    const counter = ref(0);
    const date = ref(new Date().toLocaleTimeString());
    const watchDate = ref(new Date().toLocaleTimeString());

    function counterHandler(event) {
        console.log();
        counter.value++;
    }

    watchEffect(() => {
        setInterval(() => {
            date.value = new Date().toLocaleTimeString();
        }, 100);
    });

    watch(
        {},
        () => {
            setInterval(() => {
                watchDate.value = new Date().toLocaleTimeString();
            }, 100)
        },
        {immediate: true}
    );
</script>

<template>
    <button @click="counterHandler">counter {{ counter }}</button>
    <h1>watchEffect: {{ date }}</h1>
    <h1>watch: {{ watchDate }}</h1>
</template>

<style lang="scss" scoped></style>