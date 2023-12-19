<template lang="">
    <li>
        <img :src="cardInfo.card_images[0].image_url" alt="">
        <h2 class="text-wrap text-center">
            {{ cardInfo.name }}
        </h2>
        <p class="text-center">
            {{cardInfo.archetype}}
        </p>
    </li>
</template>
<script>
export default {
    name: "CardBase",
    props: [
        "cardInfo",
    ],
    data() {
        return {
            
        }
    },
}
</script>
<style lang="scss">
    @use "../style/general.scss" as *;
</style>