<script setup>
import ViewSelectorItem from "@/components/InfoCard/ViewSelectorItem.vue"
import {ref} from "vue";

const viewSelectorList = ["Daily", "Weekly", "Monthly"];
let activeItem = ref("Weekly");
</script>

<template>
    <ul class="view-selector">
        <ViewSelectorItem
            class="view-selector__item"
            v-for="item, idx in viewSelectorList"
            :key="idx"
            :text="item"
            :class="[item === activeItem ? 'view-selector__item--active' : '']"
            @chageView="{activeItem = $event; $emit('chageView', $event)}"
            />
    </ul>
</template>

<style scoped>
.view-selector {
    display: flex;
    justify-content: space-between;
    margin: 0;
    padding: 1.25rem 2rem;
    list-style: none;
}
.view-selector__item {
    font-style: 12px;
    color: var(--blue-200);
    cursor: pointer;
}
.view-selector__item:hover,
.view-selector__item--active {
    color: #fff;
}
@media (min-width: 1024px) {
    .view-selector {
        flex-direction: column;
    }
    .view-selector__item:not(:last-child) {
        margin: 0 0 1rem 0;
    }
}
</style>