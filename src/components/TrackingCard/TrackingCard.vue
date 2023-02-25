<script setup>
const props = defineProps(["title", "timeframes", "view"]);
const period = {
    daily: "day",
    weekly: "week",
    monthly: "month"
}
</script>

<template>
    <article class="tracking-card">
        <header class="tracking-card__header">
            <h4 class="tracking-card__tittle">{{ props.title }}</h4>
            <img src="@/assets/imgaes/icon-ellipsis.svg" alt="menu" class="tracking-card__menu">
        </header>
        <div class="tracking-card__body">
            <div class="tracking-card__time">
                {{ props.timeframes[props.view].current }}hr{{ props.timeframes[props.view].current > 1 ? "s" : ""}}
            </div>
            <div class="tracking-card__prev-period">
                Last {{ period[props.view] }} - {{ props.timeframes[props.view].previous }}hr{{ props.timeframes[props.view].previous > 1 ? "s" : ""}}
            </div>
        </div>
    </article>
</template>

<style scoped>
.tracking-card {
    background: var(--blue-800);
    border-radius: var(--radii);

    padding: 1.25rem;
    position: relative;
    bottom: -2px;
}
.tracking-card__header,
.tracking-card__body {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.tracking-card__header {
    margin-bottom: 1rem;
}
.tracking-card__menu {
    cursor: pointer;
}
.tracking-card__tittle {
    margin: 0;
    font-size: var(--fs-base);
    font-weight: var(--fw-normal);
}
.tracking-card__time {
    font-size: 32px;
    font-weight: var(--fw-light);
}
.tracking-card__prev-period {
    font-size: 12px;
    font-weight: var(--fw-light);
    color: var(--blue-200);
}
@media (min-width: 1024px) {
    .tracking-card__body {
        flex-direction: column;
        align-items: flex-start;
    }
    .tracking-card__time {
        margin: 0 0 0.75rem;
        font-size: 48px;
    }
    .tracking-card__header {
        margin-bottom: 0.75rem;
    }   
}
</style>