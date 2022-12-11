<template>
    <button :type="type" :class="mode">
        <slot></slot>
        <!-- Alternatively, could accept another prop and use {{buttontext}}, but slot gives more flexibility, e.e. using svg icon -->
    </button>
</template>
<!-- To give the button an alternative look, apply the .flat css class defined here under style with:
<base-button mode="flat"></base-button> -->

<script>
export default {
    props: ['type', 'mode']
}
</script>

<style scoped>
button {
    padding: 0.75rem 1.5rem;
    font-family: inherit;
    background-color: #3a0061;
    border: 1px solid #3a0061;
    color: white;
    cursor: pointer;
}

button:hover,
button:active {
    background-color: #270041;
    border-color: #270041;
}

.flat {
    background-color: transparent;
    color: #3a0061;
    border: none;
}

.flat:hover,
.flat:active {
    background-color: #edd2ff;
}
</style>