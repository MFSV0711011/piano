<template>
    <PianoContainer/>
</template>

<script>
    import PianoContainer from "@/components/PianoContainer";
    export default {
        name: 'App',
        components: {PianoContainer},
    }
</script>

<style scoped>

#app {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>