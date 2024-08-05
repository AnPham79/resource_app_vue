<template>
    <button :type="type" :mode="mode">
        <slot></slot>
    </button>
</template>

<script>
export default {
    props : [
        'type', 'mode'
    ]
}
</script>

<style scoped>
.flat {
  background-color: transparent;
  color: #3a0061;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #edd2ff;
}
    button {
        padding: 10px 20px;
        border: none;
        outline: none;
        color: white;
        background-color: #640032;
        cursor: pointer;
        transition: 0.5s;
    }

    button:hover, button:active {
        background-color: #270041;
        transition: 0.5s;
    }
</style>