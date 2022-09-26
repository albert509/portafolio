<template>
    <div class="eva-container py-24">

        <div class="eva">
            <div class="head">
                <div class="headScreen">
                    <div class="shadow-l"></div>
                    <div class="shadow-r"></div>
                    <div class="eye e-right"></div>
                    <div class="eye e-left"></div>
                </div>
            </div>

            <div class="body">
                <div class="arm"></div>
                <div class="arm2"></div>
            </div>

            <div class="hoverer">
                <div class="circle1"></div>
                <div class="circle2"></div>
                <div class="circle3"></div>
                <div class="circle4"></div>

            </div>

        </div>


    </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>
* {
    box-sizing: border-box;

}

@keyframes flota {
    0% {
        top: 0px;
    }

    50% {
        top: 10px;
    }

    100% {
        top: 0px;
    }
}

// body{

//     margin: 0;
// }



.eva-container {
    // height: 100%;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;

    flex-direction: column;

    background-color: #5A6169;
}

.eva {
    display: flex;
    justify-content: center;
    align-items: center;

    flex-direction: column;
    position: relative;
    top: 0px;
    animation-name: flota;
    animation-duration: 1s;
    animation-iteration-count: infinite;
    animation-timing-function: ease-in-out;
}

.head {
    height: 120px; //108px;
    width: 150px;

    position: relative;
    top: 0;
    left: 0;

    background-color: #D7D7D7;

    border-top-left-radius: 100px;
    border-top-right-radius: 100px;

    border-bottom-left-radius: 50px;
    border-bottom-right-radius: 50px;

    box-shadow: inset 8px 0px 8px #a3a3a3,
        inset 0px -8px 8px #a3a3a3;

    .headScreen {
        position: absolute;
        top: 15px;
        left: calc(50% - 60px);

        height: 90px;
        width: 120px;


        border-top-left-radius: 100px;
        border-top-right-radius: 100px;

        border-bottom-left-radius: 50%;
        border-bottom-right-radius: 50%;


        background-color: #191919;

        .shadow-l {
            position: absolute;
            top: 25px;
            left: 30px;
            height: 35px;
            width: 1px;

            box-shadow: -10px 0px 15px 1px rgba(255, 255, 255, 0.5),
                -15px 0px 15px 1px rgba(255, 255, 255, 0.6),
                -20px 0px 15px 1px rgba(255, 255, 255, 0.7);
        }

        .shadow-r {
            position: absolute;
            top: 25px;
            right: 30px;
            height: 35px;
            width: 1px;

            box-shadow: 10px 0px 15px 1px rgba(255, 255, 255, 0.5),
                15px 0px 15px 1px rgba(255, 255, 255, 0.6),
                20px 0px 15px 1px rgba(255, 255, 255, 0.7);
        }

        .eye {

            position: absolute;
            top: 30px;
            height: 25px;
            width: 40px;

            border-radius: 50%;

            background: radial-gradient(circle, rgb(100, 255, 255) 0%, #2989F7 45%);

            //transform: rotateZ(20deg);
        }

        .e-right {
            transform: rotateZ(15deg);
            left: 15px;
        }

        .e-left {
            transform: rotateZ(-15deg);
            right: 15px;
        }

        &::before {
            content: '';
            position: absolute;
            bottom: 15px;
            left: calc(50% - 30px);

            height: 45px;
            width: 60px;

            border-top-left-radius: 25px;
            border-top-right-radius: 25px;

            border-bottom-left-radius: 15px;
            border-bottom-right-radius: 15px;


            background-color: rgba($color: #000000, $alpha: 1.0);
        }
    }
}

.body {
    position: relative;
    top: 0;
    left: 0;
    background-color: #D7D7D7;

    height: 230px;
    width: 170px;

    box-shadow: inset 10px 0px 10px rgba(163, 163, 163, .3),
        inset 10px 0px 20px rgba(163, 163, 163, 1),
        inset 0px -10px 20px #a3a3a3;

    margin-top: 5px;

    border-top-left-radius: 20px;
    border-top-right-radius: 20px;

    border-bottom-left-radius: 50%;
    border-bottom-right-radius: 50%;

    .arm {
        position: absolute;
        top: 13px;
        left: -40px;
        background-color: #D7D7D7;

        height: 150px;
        width: 30px;

        border-radius: 20px;

        box-shadow: inset 10px 0px 5px rgba(163, 163, 163, .3);
    }

    .arm2 {
        position: absolute;
        top: 13px;
        right: -40px;
        background-color: #D7D7D7;

        height: 150px;
        width: 30px;

        border-radius: 20px;

        box-shadow: inset 10px 0px 5px rgba(163, 163, 163, .3);
    }
}

@keyframes hondas {
    from {
        top: 0px;
        transform: scale(1) rotateX(75deg);
        opacity: 1;
    }

    to {
        top: 50px;
        transform: scale(0) rotateX(75deg);
        opacity: 0;
    }
}

.hoverer {
    position: relative;
    perspective: 600px;

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    .circle1 {
        position: absolute;
        top: 0;
        width: 100px;
        height: 50px;
        ///border: 3px solid black;
        transform: scale(1) rotateX(75deg);
        border-radius: 50%;

        box-shadow: 0px 0px 30px #f1c0e8, 0px 0px 30px transparent;

        //transform: rotateX(75deg);


    }


    .circle2 {
        position: absolute;
        top: 0;
        width: 100px;
        height: 50px;
        //border: 3px solid black;
        transform: scale(1) rotateX(75deg);
        border-radius: 50%;

        //transform: rotateX(75deg);

        box-shadow: 0px 0px 30px #f1c0e8, 0px 0px 30px transparent;

        animation-name: hondas;
        animation-duration: 0.8s;
        animation-iteration-count: infinite;
        animation-timing-function: ease-in-out;
    }

    .circle3 {
        position: absolute;
        top: 0;
        width: 100px;
        height: 50px;
        ///border: 3px solid black;
        transform: scale(1) rotateX(75deg);
        border-radius: 50%;

        //transform: rotateX(75deg);
        box-shadow: 0px 0px 30px #f1c0e8, 0px 0px 30px transparent;

        animation-name: hondas;
        animation-duration: 0.8s;
        animation-iteration-count: infinite;
        animation-delay: 0.5s;
        animation-timing-function: ease-in-out;
    }

    .circle4 {
        position: absolute;
        top: 0;
        width: 100px;
        height: 50px;
        //border: 3px solid black;
        transform: scale(1) rotateX(75deg);
        border-radius: 50%;

        //transform: rotateX(75deg);
        box-shadow: 0px 0px 30px #f1c0e8, 0px 0px 30px transparent;

        animation-name: hondas;
        animation-duration: 0.8s;
        animation-iteration-count: infinite;
        animation-delay: 1s;
        animation-timing-function: ease-in-out;
    }

}
</style>