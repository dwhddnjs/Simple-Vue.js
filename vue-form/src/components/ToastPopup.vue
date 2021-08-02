<template>
    <div class= 'toast' v-bind:class="{ 'animation': open }">
        로그인 완료 되었습니다
    </div>
</template>

<script>
let timer;


export default {
    props: ['open'],
    watch: {
        open(newValue) {
          if(newValue) {
              console.log('토스트 팝업 열기')
            clearTimeout(timer)
            timer = setTimeout(()=>this.$emit('close'),2000)
          }
      }
    }
}
</script>

<style scoped>
    .toast  {
     width: 200px;
     height: 40px;
     background: black;
     color: white;
     display: flex;
     justify-content: center;
     align-items: center;
     position: fixed;
     bottom: -5%;
     left: 5%;
     transition:bottom 0.5s linear; 
    }

.animation {
    bottom: 5%;
}
</style>



