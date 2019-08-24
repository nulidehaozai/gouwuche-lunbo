<template>
    <div id="c-banner">
        <div class="ct">
            <div class="ctc"> <img src="../assets/img/phone1.png"> </div>
            <div class="ctc"> <img src="../assets/img/phone2.png"> </div>
            <div class="ctc"> <img src="../assets/img/phone3.png"> </div>
        </div>
        <div class="cb">
            <div class="cbc"> <img src="../assets/img/n1.jpg"> </div>
            <div class="cbc"> <img src="../assets/img/n2.jpg"> </div>
            <div class="cbc"> <img src="../assets/img/n3.jpg"> </div>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
#c-banner{
    width: 100%;
    height: 102px;
}
#c-banner img{
    width: 100%;
    height: 50px;
}
#c-banner>.ct{
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100%;
    height: 50px;
    overflow: hidden;
    cursor: pointer;
}
#c-banner>.ct>.ctc{
width:25%;
height: 50px;
border-radius: 20px;
overflow: hidden;
cursor: pointer;
margin-bottom: 2px;
}
#c-banner>.cb{
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100%;
    height: 50px;
    overflow: hidden;
    cursor: pointer;
}
#c-banner>.cb>.cbc{
    width: 25%;
    height: 50px;
    border-radius: 20px;
    overflow: hidden;
    cursor: pointer;
}

</style>