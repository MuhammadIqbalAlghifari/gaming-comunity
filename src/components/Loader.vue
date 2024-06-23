<template>
    <div id="loader" class="loader">
      <div></div>
    </div>
</template>

<script setup>
</script>

<style scoped>

.loader {
position: fixed;
top: 0;
left: 0;
width: 100vw;
height: 100vh;
display: flex;
align-items: center;
justify-content: center;
background-color: black;
}

.loader div {
width: 15px;
aspect-ratio: 1;
border-radius: 50%;
animation: l5 1s infinite linear alternate;
}

@keyframes l5 {
    0% {
    box-shadow: 20px 0 #fff, -20px 0 #fff2;
    background: #fff;
    }
    33% {
    box-shadow: 20px 0 #fff, -20px 0 #fff2;
    background: #fff2;
    }
    66% {
    box-shadow: 20px 0 #fff2, -20px 0 #fff;
    background: #fff2;
    }
    100% {
    box-shadow: 20px 0 #fff2, -20px 0 #fff;
    background: #fff;
    }
}
    
</style>