<template>
    <div class="k-container text-black p-16 bg-[#e9d8a6]">

        <div id="frame" class="frame">

            <div class="outlined paper-shadow"></div>

            <div class="outline-oreja or-out-left paper-shadow"></div>

            <div class="outline-oreja or-out-right paper-shadow"></div>

            <div class="outlined"></div>

            <div class="outline-oreja or-out-left"></div>

            <div class="outline-oreja or-out-right"></div>

            <div class="oreja or-left">

                <div class="detail-1"></div>
                <div class="detail-2"></div>

            </div>

            <div class="oreja or-right">

                <div class="detail-1"></div>
                <div class="detail-2"></div>

            </div>


            <div class="cabeza">

            </div>

            <div class="ceja c-left"></div>
            <div class="ceja c-right"></div>

            <div class="ojo derecho">
                <div id="r-b" class="bolita"></div>
            </div>

            <div class="ojo izquierdo">
                <div id="l-b" class="bolita"></div>
            </div>

            <div class="puntos p-derecho">
                <div class="punto"></div>
                <div class="punto"></div>
                <div class="punto"></div>
            </div>
            <div class="puntos p-izquierdo">
                <div class="punto"></div>
                <div class="punto"></div>
                <div class="punto"></div>
            </div>



            <div id="sonrisa" class="sonrisa"></div>

            <div class="buche bu-left">/ /////</div>
            <div class="buche bu-right">///// /</div>

            <div class="punchHole"></div>

        </div>

    </div>
</template>

<script setup>

onMounted(() => {

    let bolitaDerecha = document.getElementById('r-b')
    let bolitaIzq = document.getElementById('l-b')
    let sonrisa = document.getElementById('sonrisa')

    let frame = document.getElementById('frame')

    let cejas = document.getElementsByClassName('ceja');
    

    frame.addEventListener('click', (e) => {

        for (let ceja of cejas) {
            ceja.classList.toggle('freco');
        }

        setTimeout(() => {

            for (let ceja of cejas) {
                ceja.classList.toggle('freco');
            }

        }, 1000);

    })

    window.addEventListener('mousemove', (e) => {

        let pantallaH = window.innerWidth;
        let pantallaY = window.innerHeight;

        let porciento = (e.x / pantallaH) * 100;

        let porcientoH = (e.y / pantallaY) * 100;

        // console.log(porciento)

        if (porciento > 3 && porciento < 80) {

            bolitaDerecha.style.left = `${porciento}%`
            bolitaIzq.style.left = `${porciento}%`

        }

        sonrisa.style.borderRadius = `${porcientoH}%`;



    })


})

</script>

<style lang="scss" scoped>
* {
    margin: 0;

}

.k-container {

    display: flex;
    justify-content: center;
    align-items: center;

    height: 100%;
    width: 100%;

    // padding: 16px;

    // background: #e9d8a6;

}

.imgTemplate {

    position: absolute;

    opacity: 0.2;

}

.punchHole {
    position: absolute;
    top: -20px;
    left: calc(50% - 12.5px);

    height: 25px;
    width: 25px;
    border-radius: 50%;
    background-color: #e9d8a6;
    border: 2px solid rgba(250, 250, 250, 0.3);
    box-shadow: inset 3px 3px 3px rgba(0, 0, 0, 0.3);
}

.frame {

    position: relative;

    cursor: pointer;

}

.cabeza {

    position: relative;
    top: 40px;

    height: 290px; //300px;
    width: 220px;
    border-top-left-radius: 110px;
    border-top-right-radius: 110px;

    border-bottom-left-radius: 100px;
    border-bottom-right-radius: 100px;

    transform: perspective(10px) rotateX(-1deg);

    border: 3px solid black;
    background: #FFCEB5;

    box-shadow: inset 8px 7px 0px #ffe8dd, //#FFF7EA,
        inset -10px -10px 0px #FFA176;

    //outline: 10px solid white;

}

.ojo {

    transform: perspective(0px) rotateX(0deg);

    position: absolute;
    bottom: 93px;

    width: 63px;
    height: 5px;

    background: black;
    border-radius: 100px;

    .bolita {
        //content: '';
        position: absolute;
        top: 0px;
        //left: 40%;//14px;
        height: 12px;
        width: 12px;
        background: black;

        border-radius: 50%;
    }

    #r-b {
        right: 14px;
    }

    #l-b {
        left: 14px;
    }

}

.derecho {
    left: 32px;
}

.izquierdo {

    //transform: rotateY(180deg);
    right: 32px;

}

.puntos {

    perspective: none !important;

    display: flex;
    flex-direction: column;

    gap: 20px;

    position: absolute;
    top: 80px;
    //left: 98px;

    .punto {
        height: 8px;
        width: 8px;
        background: #B35E2F;
        border-radius: 50%;
    }

}

.p-derecho {
    left: 98px;
}

.p-izquierdo {
    right: 95px;
}

.sonrisa {

    position: absolute;
    bottom: 23px;
    left: 70px;

    height: 140px;
    width: 80px;
    border: 5px solid black;

    border-color: transparent transparent black transparent;

    border-radius: 50%;


}

.ceja {

    position: absolute;
    top: 100px;
    // left: 23px;
    background: black;

    height: 110px;
    width: 70px;

    border-radius: 50%;

    transform: rotateZ(-30deg) scale(0.8);

    &::after {
        content: '';
        position: absolute;
        top: 15px;
        right: 8px;
        height: 110px;
        width: 70px;
        background: #FFCEB5;
        border-radius: 50%;
        transform: rotateZ(-15deg);
    }

}

.c-left {

    left: 23px;

}

.c-right {
    right: 20px;
    transform: rotateY(180deg) rotateZ(-30deg) scale(0.8);
}

.buche {
    position: absolute;
    bottom: 55px;

    font-weight: bold;
    //font-size: large;

    filter: blur(1px);

    transform: skew(-30deg) scaleY(0.5);
}

.bu-left {
    left: 40px;
}

.bu-right {
    right: 40px;
}

.oreja {
    height: 110px;
    width: 60px;
    position: absolute;
    // left: -35px;
    top: 140px;
    background: #FFCEB5;

    // border-radius: 200px;

    border-top-left-radius: 50%;
    border-top-right-radius: 50%;

    border-bottom-left-radius: 50%;

    transform: rotate(-23deg);

    border: 3px solid black;

    overflow: hidden;

    box-shadow: inset 4px 3px 1px #FFF7EA;

    .detail-1 {

        position: absolute;
        top: 15px;
        left: 8px;

        height: 60px;
        width: 30px;

        border: 3px solid black;

        border-color: black black transparent transparent;

        border-radius: 50%;

        box-shadow: inset -10px -0px 0px #FFA176;

    }

    .detail-2 {

        position: absolute;
        top: 40px;
        left: 20px;

        height: 40px;
        width: 20px;

        border: 3px solid black;

        border-color: black black black black;

        border-radius: 50%;

        background-color: #FFCEB5;

        box-shadow: inset -10px -15px 3px #FFA176;

    }
}

.or-left {
    left: -35px;
}

.or-right {
    right: -35px;
    transform: rotateY(180deg) rotate(-23deg);
}



@keyframes cejasFrecas {

    0% {
        top: 100px;
    }

    50% {
        top: 50px;
    }

    100% {
        top: 100px;
    }

}

.freco {
    animation-name: cejasFrecas;
    animation-iteration-count: 3;
    animation-duration: .3s;
}

.outlined {
    position: absolute;
    //outline: 10px solid white;

    height: 290px; //300px;
    width: 220px;
    border-top-left-radius: 110px;
    border-top-right-radius: 110px;

    border-bottom-left-radius: 100px;
    border-bottom-right-radius: 100px;

    transform: perspective(10px) rotateX(-1deg) scale(1.08);

    border: 3px solid transparent;
    background: white;

    top: 45px;

    //box-shadow: 0px 0px 10px rgba(0,0,0,0.5);
}

.outline-oreja {
    height: 110px;
    width: 60px;
    position: absolute;
    // left: -35px;
    top: 140px;
    background: white;

    // border-radius: 200px;

    border-top-left-radius: 50%;
    border-top-right-radius: 50%;

    border-bottom-left-radius: 50%;

    transform: rotate(-23deg) scale(1.3);

    border: 3px solid white;

    overflow: hidden;

    //box-shadow: 0px 0px 10px rgba(0,0,0,0.5);

    //box-shadow: inset 4px 3px 1px #FFF7EA;
}

.or-out-left {
    left: -35px;

}

.or-out-right {
    right: -35px;
    transform: rotateY(180deg) rotate(-23deg) scale(1.3);
}

.paper-shadow {
    box-shadow:
        0px 0px 0px rgba(0, 0, 0, 0.2),
        0px 0px 2px rgba(0, 0, 0, 0.2),
        0px 0px 4px rgba(0, 0, 0, 0.2),
        0px 0px 8px rgba(0, 0, 0, 0.2),
        0px 0px 16px rgba(0, 0, 0, 0.2);

}

//*{
//border-radius: 0px !important;
//}
</style>