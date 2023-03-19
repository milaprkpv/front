<script setup>
    import { reactive, ref, watchEffect, watch } from 'vue';
    const counter = ref(0);
    const date1 = ref(new Date().toLocaleTimeString());
    const date2 = ref(new Date().toLocaleTimeString());
    function counterHandler(event) {
        console.log();
    }
    watchEffect(() => {
        setInterval(() => {
            date1.value = new Date().toLocaleTimeString()
        }, 1000)
    });
    watch({}, () => {
        setInterval(() => {
            date2.value = new Date().toLocaleTimeString()
        }, 1000)
    },
    { immediate: true });
</script>


<template>
    <button @click="counterHandler">counter {{ counter }}</button>
    <h1>{{ date1 }}</h1>
    <h2>{{ date2 }}</h2>
</template>


<style lang="scss" scoped>

</style>