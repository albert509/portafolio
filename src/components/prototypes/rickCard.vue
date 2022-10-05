<template>
    <div class="card-container text-black flex h-full justify-center bg-[#9DB19C] py-10">

        <div class="movingCard-back">
            <div class="octagono scale-down-to-card"></div>
            <div class="brand-name">
                Web art collection
            </div>
        </div>

        <div id='rickCard' class="movingCard">



            <div class="innerFrame">

                <div class="cara-frame">

                    <div class="mechon-1"></div>
                    <div class="pelo"></div>

                    <div class="oreja-left"></div>
                    <div class="oreja-right"></div>

                    <div class="cara">

                        <div class="nariz"></div>

                        <div class="ojo-outer">
                            <div class="ojo">
                                <div class="bolita"></div>
                            </div>
                            <div class="circle-break"></div>

                            <div class="ojera"></div>
                        </div>
                        <div class="ojo-outer">
                            <div class="ojo left">
                                <div class="bolita"></div>
                            </div>
                            <div class="circle-break-left"></div>

                            <div class="ojera-left"></div>
                        </div>

                        <div class="mono-eja"></div>

                        <div class="buche-left"></div>
                        <div class="buche-right"></div>
                        <div class="boca"></div>
                    </div>
                </div>

                <div class="card-title">
                    Rick el calvo
                </div>

            </div>

            <div class="number-circle">
                1
            </div>

            <div class="qr-container">
                <img src='https://chart.googleapis.com/chart?cht=qr&chl=lo%20escaneaste%20curioso&chs=60x60&choe=UTF-8&chld=L|2'
                    alt=''>

                <div class="description">
                    <small>Un Rick creado usando HTML y CSS.</small>
                </div>
            </div>


        </div>
    </div>
</template>

<script setup>

onMounted(() => {

    let rickCard = document.getElementById('rickCard');

    let ojos = document.querySelectorAll('.bolita');

    window.addEventListener('mousemove', (e) => {

        let pantallaH = window.innerWidth;
        let pantallaY = window.innerHeight;

        let porcientoH = (e.x / pantallaH) * 100;

        let porcientoY = (e.y / pantallaY) * 100;

        // console.log(porciento)

        if (porcientoY > 44 && porcientoY < 85) {

            ojos.forEach(o => o.style.top = `${porcientoY}%`)

        }

        if (porcientoH > 18 && porcientoH < 70) {

            ojos.forEach(o => o.style.left = `${porcientoH}%`)

        }

        let degY = porcientoH > 50 ? 30 : -30;

        let degX = porcientoY > 50 ? -30 : 30;

        rickCard.style.transform = `rotateY(${degY}deg) rotateX(${degX}deg)`;

    })

    document.addEventListener("mouseleave", (event) => {
        rickCard.style.transform = 'none';
    });

})

</script>

<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Syne+Mono&display=swap');

* {
    box-sizing: border-box;
}

$color-piel: rgb(235, 215, 206);
$color-pelo: rgb(181, 239, 253);
$borders-thickness: 4px;

.cara-frame {

    position: relative;
    top: 0;
    left: 0;

    transform: scale(0.5);

}

.cara {
    position: relative;
    top: 0;
    left: 0;

    height: 415.19px;
    width: 256.962px;

    background-color: $color-piel;
    border: $borders-thickness solid black;

    box-shadow: inset -3px -3px 10px rgba(0, 0, 0, 0.7);

    border-radius: 200px;

    .ojo {
        position: absolute;
        top: 100px;
        left: -15px;

        height: 110px;
        width: 110px;
        border-radius: 50%;
        border: $borders-thickness solid black;

        background-color: white;

        box-shadow: inset -3px -3px 5px rgba(0, 0, 0, 0.7);

        overflow: hidden;

        &::before {
            content: '';
            position: absolute;
            bottom: 60px;
            left: 0px;
            width: 200px;
            height: 200px;
            background-color: $color-piel;
            border-bottom: $borders-thickness solid black;
        }

        .bolita {
            content: '';
            position: absolute;
            top: 44%;
            left: 18%;

            width: 15px;
            height: 15px;
            border-radius: 50%;
            background-color: black;
        }
    }

    .ojera {
        position: absolute;
        top: 200px;
        left: 0;
        height: 20px;
        width: 70px;

        border-radius: 50%;

        //border: $borders-thickness solid black;

        box-shadow: 0px 3.5px 0px rgba(0, 0, 0, 1);

        transform: rotateZ(10deg);
    }

    .ojera-left {
        position: absolute;
        top: 190px;
        left: 150px;
        height: 30px;
        width: 70px;

        border-radius: 50%;

        //border: $borders-thickness solid black;

        box-shadow: 0px 3.5px 0px rgba(0, 0, 0, 1);

        transform: rotateZ(-17deg);
    }

    .mono-eja {
        position: absolute;
        top: 75px;
        left: -10px;

        height: 27px;
        width: 220px;
        background-color: $color-pelo;
        border: $borders-thickness solid black;
        border-radius: 43%;

        box-shadow: inset -3px -3px 5px rgba(0, 0, 0, 0.7);
    }

    .nariz {
        position: absolute;
        top: 135px;
        left: 0;
        height: 45px;
        width: 220px;

        background-color: $color-piel;
        border: $borders-thickness solid black;
        border-radius: 50%;

        transform: rotateZ(108deg);

        box-shadow: 1px -3px 5px rgba(0, 0, 0, 0.5);

        &::after {
            content: '';
            position: absolute;
            top: -5px;
            left: -20px;
            height: 60px;
            width: 125px;
            background-color: $color-piel;
        }

        &::before {
            content: '';
            position: absolute;
            bottom: 10px;
            right: 58px;
            height: 60px;
            width: 60px;
            background-color: $color-piel;

        }
    }

    .boca {
        position: absolute;
        bottom: 100px;
        left: 10px;

        //height: 100px;
        width: 160px;

        border-top: $borders-thickness solid black;

        //border-radius: 20px;

        transform: rotateZ(5deg);
    }

    .buche-left {
        position: absolute;
        bottom: 80px;
        left: -10px;

        height: 50px;
        width: 120px;
        background-color: $color-piel;

        border-radius: 50%;
        border: $borders-thickness solid black;
        transform: rotateZ(5deg);

        &::before {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 20px;

            height: 60px;
            width: 120px;
            background-color: $color-piel;


        }
    }

    .buche-right {
        position: absolute;
        bottom: 78px;
        right: 60px;

        height: 50px;
        width: 120px;
        background-color: $color-piel;

        border-radius: 50%;
        border: $borders-thickness solid black;
        transform: rotateZ(12deg);

        box-shadow: 3px 0px 5px rgba(0, 0, 0, 0.5);

        &::before {
            content: '';
            position: absolute;
            top: -5px;
            right: 20px;

            height: 55px;
            width: 120px;
            background-color: $color-piel;

        }

        &::after {

            content: '';
            position: absolute;
            top: -10px;
            right: 20px;

            height: 55px;
            width: 55px;
            background-color: $color-piel;

        }
    }


}

.oreja-left {
    position: absolute;
    bottom: 125px;
    left: -20px;
    height: 80px;
    width: 60px;

    background-color: $color-piel;
    border: $borders-thickness solid black;
    border-radius: 50%;

    transform: rotateZ(-30deg);
}

.oreja-right {
    position: absolute;
    bottom: 125px;
    right: -25px;
    height: 80px;
    width: 70px;

    background-color: $color-piel;
    border: $borders-thickness solid black;
    border-radius: 50%;

    transform: rotateZ(90deg);

    box-shadow: inset -3px 3px 5px rgba(0, 0, 0, 0.7);
}

.pelo {

    position: absolute;
    bottom: 50px;
    left: -70px;

    height: 400px;
    width: 400px;

    background-color: $color-pelo;
    //border: $borders-thickness solid black;

    border-radius: 50%; //200px;




}

.circle-break {
    position: absolute;
    top: 75px;
    left: 25px;
    height: 50px;
    width: 50px;
    background-color: $color-piel;
}

.circle-break-left {
    position: absolute;
    top: 75px;
    left: 25px + 110px;
    height: 50px;
    width: 70px;
    background-color: $color-piel;
}

.left {
    left: 110px !important;
}

.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    width: 100vw;

    perspective: 400px; // para que el efecto 3d tenga efectos
}

.octagono {
    position: relative;
    top: 0;
    left: 0;

    border: 2px solid white;

    height: 431px;
    width: 249px;
    box-sizing: border-box;

    transform: scale(0.5);

    &::after {
        content: '';

        position: absolute;
        top: 0;
        left: 0;

        border: 2px solid white;

        height: 431px;
        width: 249px;

        transform: rotateZ(60deg);
        box-sizing: border-box;
    }

    &::before {
        content: '';

        position: absolute;
        top: 0;
        left: 0;

        border: 2px solid white;

        height: 431px;
        width: 249px;

        transform: rotateZ(120deg);
        box-sizing: border-box;
    }
}

.peeledTag {
    position: relative;
    top: 0;
    left: 0;
    height: 100px;
    width: 100px;

    background-color: blue;

    overflow: hidden;

    &::before {
        content: '';

        position: absolute;
        top: -100px;
        right: -100px;
        height: 100px;
        width: 100px;

        transition: all .6s;

        background-color: rgb(0, 0, 100);
    }

    &::after {
        content: '';

        position: absolute;
        top: -85px;
        right: -85px;
        height: 100px;
        width: 100px;
        transition: all .6s;

        transform: rotateZ(45deg);

        background-color: rgb(255, 255, 255);
    }

    &:hover::before {
        top: -50px;
        right: -50px;
    }

    &:hover::after {
        top: -60px;
        right: -60px;
    }


}


@keyframes card-rotation {

    0% {
        transform: rotateY(0deg);
        box-shadow: 15px -15px 30px rgba(0, 0, 0, 0.3);
    }

    100% {
        transform: rotateY(360deg);
        box-shadow: 15px -15px 30px rgba(0, 0, 0, 0.3);
    }
}

@keyframes card-rotation-back {

    0% {
        transform: rotateY(180deg);
        box-shadow: 15px -15px 30px rgba(0, 0, 0, 0.3);
    }

    100% {
        transform: rotateY(540deg);
        box-shadow: 15px -15px 30px rgba(0, 0, 0, 0.3);
    }
}

.card-container {
    perspective: 1200px;
    position: relative;
    top: 0;
    left: 0;
}

.movingCard {

    position: relative;
    top: 0;
    left: 0;

    height: 450px;
    width: 270px;

    background-color: cadetblue;
    //background-image: url("https://i.pinimg.com/736x/5c/cd/75/5ccd7544f3908ca293f66e9b186015df.jpg");
    background-size: contain;
    border: 2px solid black;

    transition: all 0.4s;

    padding: 25px;


    overflow: hidden;


    //transform: scale(0.3);//rotate3d(0,40,10,60deg);

    box-shadow: 15px -15px 30px rgba(0, 0, 0, 0.3);

    backface-visibility: hidden;

    //animation-name: card-rotation;
    animation-duration: 8s;
    animation-iteration-count: infinite;

    &::before {
        content: '';
        position: absolute;
        bottom: -30px;
        left: -30px;

        height: 60px;
        width: 60px;

        box-sizing: border-box;

        box-shadow: 0px -5px 10px 5px rgba(0, 0, 0, 0.3);

        //background-color: cadetblue;
        border-top: 2px solid black;
        transform: rotateZ(45deg);
    }

    &::after {
        content: '';
        position: absolute;
        bottom: -30px;
        right: -30px;

        height: 60px;
        width: 60px;



        box-sizing: border-box;

        box-shadow: 0px -5px 10px 5px rgba(0, 0, 0, 0.3);

        //background-color: cadetblue;
        border-top: 2px solid black;
        transform: rotateZ(-45deg);
    }

    .number-circle {
        display: flex;
        justify-content: center;
        align-items: center;
        position: absolute;
        top: 25px;
        left: 25px;
        height: 40px;
        width: 40px;
        border-radius: 50%;

        border: 2px solid black;

        background-color: rgb(230, 230, 230);

        font-weight: bold;

        font-family: 'Syne Mono', monospace;
    }

    .qr-container {
        display: flex;
        margin-top: 8px;

        img {
            height: 60px;
        }

        .description {
            padding: 5px;
            font-weight: bold;
            color: rgba(0, 0, 0, 0.8);
            //text-shadow: 1px 1px 1px rgba(0,0,0,0.3);
            margin-left: 3px;
            width: 150px;
            height: 60px;
            background-color: rgb(230, 230, 230);

            font-family: 'Syne Mono', monospace;
        }
    }

    .o-contain {
        object-fit: cover;
        height: 100%;
        width: 100%;
    }


    .innerFrame {
        position: relative;
        top: 0;
        left: 0;
        height: 300px;
        //width: 200px;
        background-color: rgb(230, 230, 230);
        display: flex;
        justify-content: center;
        align-items: center;

        object-fit: contain;

        //overflow: hidden;

        border: 2px solid black;

        &::before {
            content: '';
            position: absolute;
            top: -30px;
            left: -30px;

            height: 60px;
            width: 60px;

            box-sizing: border-box;

            background-color: cadetblue;
            border-right: 2px solid black;
            transform: rotateZ(45deg);
        }

        &::after {
            content: '';
            position: absolute;
            bottom: -30px;
            right: -30px;

            height: 60px;
            width: 60px;

            // background: url('https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/Unofficial_JavaScript_logo_2.svg/2048px-Unofficial_JavaScript_logo_2.svg.png');

            background-size: contain;

            box-sizing: border-box;

            background-color: cadetblue;
            border-left: 2px solid black;
            transform: rotateZ(45deg);
        }

        .card-title {
            padding: 5px;
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 30px;
            border-top: 2px solid black;
            background-color: white;

            font-weight: bold;

            font-family: 'Syne Mono', monospace;
        }


    }

    &-back {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;

        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        color: white;
        font-family: 'Syne Mono', monospace;
        font-size: 24px;

        background-color: brown;
        border: 2px solid black;

        transform: rotateY(180deg);
        backface-visibility: hidden;

        //animation-name: card-rotation-back;
        animation-duration: 8s;
        animation-iteration-count: infinite;


    }
}
</style>