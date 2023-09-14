<script>

export default {
    data() {
        return {}
    },

    props: {
        loadingText: String,
    }
}
</script>

<template>
    <div class="loading-container">
        <font-awesome-icon icon="spinner" size="3x" spin />
       <h3>{{ loadingText || 'Loading' }}  </h3> 
    </div>
</template>

<style lang="scss" scoped>
.loading-container {
    position: fixed;
    z-index: 10;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    backdrop-filter: blur(10px);

    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1rem;

    h3 {
        font-weight: 800;
    }

}
</style>
