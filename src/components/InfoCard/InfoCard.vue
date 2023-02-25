<template>
    <div class="info-card">
        <img class="info-card__photo" src="@/assets/imgaes/image-jeremy.png" alt="Photo Jeremy Robson">
        <div class="info-card__text">
            <p class="info-card__subtittle">Report for</p>
            <h3 class="info-card__tittle">Jeremy Robson</h3>
        </div>
    </div>
</template>

<style scoped>
.info-card {
    background: var(--blue-500);
    border-radius: var(--radii);
    padding: 2rem;

    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1rem;
}
.info-card__photo {
    width: 50px;
    height: 50px;
    border: 3px solid #fff;
    border-radius: var(--radii-full);
}
.info-card__subtittle {
    font-weight: var(--fw-light);
    margin: 0;
    font-size: 12px;
}
.info-card__tittle {
    font-weight: var(--fw-light);
    margin: 0.5rem 0 0;
}

@media (min-width: 1024px) {
    .info-card {
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-start;
    flex-grow: 1;
  }
  .info-card__photo {
        width: 70px;
        height: 70px;
        margin: 0 0 1.5rem 0;
    }
    .info-card__tittle {
        font-size: 30px;
    }
}
</style>