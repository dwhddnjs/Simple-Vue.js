<template>
  <div class='progress'>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
    .progress {
        height: 10px;
        background: lime;
        width: 50%;
        transition: width 700ms linear;
        border-radius: 10px;
        animation: loading 1s linear
    }

    .complete {
        width: 100%;
    }

    @keyframes loading {
        0%{
            width: 0%;
        }
        50% {
            width: 50%;
        }
        100% {
            width: 100%;
        }
    }
</style>