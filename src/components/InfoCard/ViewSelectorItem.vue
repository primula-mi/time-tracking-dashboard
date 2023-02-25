<script setup>
const props = defineProps(["text"]);

</script>
<template>
    <li
    class="view-selector__item"
    @click="$emit('chageView', props.text)"
    >{{ props.text }}</li>
</template>