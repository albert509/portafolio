<template>

    <div class="bg-[#C3C5A1] text-black w-full h-[547px]">

        <div class="gb-container">
    
            <!-- <div class="clicky-btn"></div> -->
    
            <div class="game-boy">
    
                <div class="lines-section">
                    <div class="line1"></div>
                    <div class="line2"></div>
                    <div class="line3"></div>
                </div>
    
                <div class="screen-section">
                    <div class="power">
                        <div class="led"></div>
                        <small>Battery</small>
                    </div>
                    <div class="screen"></div>
                </div>
    
                <div class="controles">
                    <div class="d-container">
                        <div class="d-pad">
    
                            <div id="top" class="clicky-btn top">
                                <div class="center-triengle"></div>
                            </div>
                            <div id="left" class="clicky-btn left">
                                <div class="center-triengle"></div>
                            </div>
                            <div id="right" class="clicky-btn right">
                                <div class="center-triengle"></div>
                            </div>
                            <div id="bottom" class="clicky-btn bottom">
                                <div class="center-triengle"></div>
                            </div>
    
                            <div class="d-pad-center">
                                <div class="center-circle"></div>
                            </div>
    
                        </div>
                    </div>
    
    
    
                    <div class="action-b">
    
                        <div class="a-btn">A</div>
                        <div class="b-btn">B</div>
    
                    </div>
                </div>
    
                <div class="start-select">
    
                    <div class="inclinador">
                        <div class="ss-btn-container">
                            <div class="ss-btn"></div>
                        </div>
                        <small>SELECT</small>
                    </div>
    
                    <div class="inclinador">
                        <div class="ss-btn-container">
                            <div class="ss-btn"></div>
                        </div>
                        <small>START</small>
                    </div>
    
                </div>
    
                <div class="speaker">
    
                    <div></div>
                    <div></div>
                    <div></div>
                    <div></div>
                    <div></div>
                    <div></div>
                    <div></div>
    
                </div>
    
    
    
            </div>
    
    
    
        </div>

    </div>
</template>

<script setup>

onMounted(() => {

    nextTick(() => {

        document.addEventListener('DOMContentLoaded', (ev) => {

            let left = document.querySelector('#left');
            let right = document.querySelector('#right');
            let top = document.querySelector('#top');
            let bottom = document.querySelector('#bottom');

            let aBtn = document.querySelector('.a-btn');
            let bBtn = document.querySelector('.b-btn');

            let dPad = document.querySelector('.d-pad');

            let keyPressed = [];

            let rotation = 5;

            let evaluateDirection = () => {

                if (keyPressed.includes('left') && keyPressed.includes('top')) {

                    dPad.style.transform = `rotateX(${rotation}deg) rotateY(-${rotation}deg)`;

                }
                if (keyPressed.includes('left') && keyPressed.includes('bottom')) {

                    dPad.style.transform = `rotateX(-${rotation}deg) rotateY(-${rotation}deg)`;
                }
                if (keyPressed.includes('right') && keyPressed.includes('top')) {

                    dPad.style.transform = `rotateX(${rotation}deg) rotateY(${rotation}deg)`;
                }
                if (keyPressed.includes('right') && keyPressed.includes('bottom')) {

                    dPad.style.transform = `rotateX(-${rotation}deg) rotateY(${rotation}deg)`;
                }



                if (keyPressed.length === 1 && keyPressed[0] === 'right') {

                    dPad.style.transform = `rotateY(${rotation}deg)`;
                }
                if (keyPressed.length === 1 && keyPressed[0] === 'left') {

                    dPad.style.transform = `rotateY(-${rotation}deg)`;
                }
                if (keyPressed.length === 1 && keyPressed[0] === 'top') {

                    dPad.style.transform = `rotateX(${rotation}deg)`;
                }
                if (keyPressed.length === 1 && keyPressed[0] === 'bottom') {

                    dPad.style.transform = `rotateX(-${rotation}deg)`;
                }

                if (keyPressed.length === 0) {

                    dPad.style.transform = 'rotateX(0deg) rotateY(0deg)';
                }

            }


            window.addEventListener('keydown', (e) => {

                e.preventDefault();

                if (e.key === 'ArrowLeft') {
                    left.classList.add('is-pressed');
                    keyPressed.push('left');
                }
                if (e.key === 'ArrowRight') {
                    right.classList.add('is-pressed-alt');
                    keyPressed.push('right');
                }
                if (e.key === 'ArrowUp') {
                    top.classList.add('is-pressed');
                    keyPressed.push('top');
                }
                if (e.key === 'ArrowDown') {
                    bottom.classList.add('is-pressed');
                    keyPressed.push('bottom');
                }

                if (e.key === 'a') {

                    aBtn.classList.add('a-b-pressed');
                    keyPressed.push('a');

                }
                if (e.key === 'b') {

                    bBtn.classList.add('a-b-pressed');
                    keyPressed.push('b');

                }

                evaluateDirection();

            })


            window.addEventListener('keyup', (e) => {

                e.preventDefault();

                if (e.keyCode === 37) {

                    //dPad.style.transform = 'rotateY(0deg)';

                    left.classList.remove('is-pressed');

                    keyPressed = keyPressed.filter(key => key !== 'left');

                    evaluateDirection();
                }
                else if (e.keyCode === 39) {

                    //dPad.style.transform = 'rotateY(0deg)';

                    right.classList.remove('is-pressed-alt');

                    keyPressed = keyPressed.filter(key => key !== 'right');

                    evaluateDirection();

                }
                else if (e.keyCode === 38) {

                    //dPad.style.transform = 'rotateX(0deg)';

                    top.classList.remove('is-pressed');

                    keyPressed = keyPressed.filter(key => key !== 'top');

                    evaluateDirection();

                }
                else if (e.keyCode === 40) {

                    //dPad.style.transform = 'rotateX(0deg)';

                    bottom.classList.remove('is-pressed');

                    keyPressed = keyPressed.filter(key => key !== 'bottom');

                    evaluateDirection();

                }

                else if (e.key === 'a') {

                    aBtn.classList.remove('a-b-pressed');
                    keyPressed = keyPressed.filter(key => key !== 'a');

                }
                else if (e.key === 'b') {

                    bBtn.classList.remove('a-b-pressed');
                    keyPressed = keyPressed.filter(key => key !== 'b');

                }

            })



        })

    })

})

</script>

<style lang="scss" scoped>
* {
    box-sizing: border-box;
}

.gb-container {
    display: flex;
    //flex-direction: column;
    align-items: center;
    justify-content: center;
    // height: 100%;
    // width: 100%;

    // margin-top: -100px;

    // overflow: hidden;

    // perspective: 400px;

    //gap: 120px;

    transform: scale(.60);

    // background-color: #C3C5A1;
}

.game-boy {

    margin-top: -100px;

    position: relative;

    display: flex;
    flex-direction: column;

    align-items: center;
    justify-content: center;

    overflow: hidden;

    width: 420px;

    padding: 40px; //60px 40px 40px;
    padding-bottom: 100px;
    padding-top: 60px;

    background-color: #E5E5E5;

    border: 3px solid black;

    border-radius: 20px;
    border-bottom-right-radius: 80px;

    box-shadow: inset 3px 3px 20px rgba(0, 0, 0, 0.3),
        inset 0px -3px 40px rgba(0, 0, 0, 0.3),
        inset -3px -3px 0px rgba(0, 0, 0, 0.3);

    .lines-section {

        width: 100%;
        height: 45px;

        position: absolute;
        top: 0px;
        left: 0px;

        .line1 {

            position: absolute;
            bottom: 0px;

            width: 100%;
            height: 8px;
            background-color: #E5E5E5;
            box-shadow: inset 0px -2px 6px rgba(0, 0, 0, 0.5);

            //background-color: red;

        }

        .line2 {
            position: absolute;
            top: -3px;
            left: 45px;
            height: 89%;
            width: 8px;
            background-color: #E5E5E5;
            box-shadow: inset 0px 5px 6px rgba(0, 0, 0, 0.4);
        }

        .line3 {
            position: absolute;
            top: -3px;
            right: 45px;
            height: 89%;
            width: 8px;
            background-color: #E5E5E5;
            box-shadow: inset 0px 5px 6px rgba(0, 0, 0, 0.4);
        }

    }

    .screen-section {

        position: relative;

        height: 300px;
        width: 100%;

        background-color: #546678;

        border-radius: 20px;
        border-bottom-right-radius: 80px;

        border: 3px solid black;

        margin-bottom: 100px;

        padding: 30px 0px;

        display: flex;
        justify-content: center;
        align-items: center;

        .screen {
            height: 100%;
            width: 60%;
            background-color: #8AD43D;
            border: 3px solid black;

            box-shadow: inset 5px 5px 6px rgba(0, 0, 0, 0.5);
        }

        .power {
            position: absolute;
            top: 40%;
            left: 10px;

            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;

            color: white;

            .led {
                background-color: red;
                height: 10px;
                width: 10px;
                border-radius: 50%;
                border: 2px solid black;
            }
        }

    }

    .controles {

        width: 125%;

        display: flex;
        align-items: center;
        justify-content: space-between;


        //gap: 100px;

        margin-top: -50px;

        transform: scale(.80);

    }

    .start-select {

        display: flex;
        justify-content: center;
        align-items: center;

        transform: scale(.7);
        gap: 10px;

        margin-top: -10px;


        .inclinador {

            text-align: center;
            transform: rotateZ(-30deg);

            .ss-btn-container {

                padding: 5px;
                border-radius: 50px;
                box-shadow: inset 3px 3px 3px rgba(0, 0, 0, 0.3);

                .ss-btn {
                    height: 15px;
                    width: 60px;
                    border-radius: 50px;
                    background-color: rgba(0, 0, 0, 0.8);
                    box-shadow: inset 4px 4px 6px rgba(255, 255, 255, 0.4);
                }

            }



        }

    }

    .speaker {

        position: absolute;
        bottom: 25px;
        right: 35px;

        display: flex;
        flex-direction: column;
        gap: 5px;

        transform: rotateZ(50deg);

        div {

            position: relative;
            height: 10px;
            width: 70px;
            background-color: #E5E5E5;
            border-radius: 50px;

            box-shadow: inset 1px 1px 3px rgba(0, 0, 0, 0.7);

            overflow: hidden;

        }
    }

}

.action-b {

    position: relative;
    //height: 100px;
    //width: 100px;

    padding: 15px 10px;

    margin-right: 30px;

    border-radius: 200px;

    transform: rotateZ(50deg);


    box-shadow: inset 5px 5px 10px rgba(0, 0, 0, 0.3);

    .a-btn {
        display: flex;
        align-items: center;
        justify-content: center;

        height: 60px;
        width: 60px;
        border-radius: 50%;

        //margin-left: auto;
        margin-bottom: 20px;
        background-color: #C44096;
        //box-shadow: 3px 3px 0px rgb(252, 171, 162);

        transform: rotateZ(-50deg);

        box-shadow: inset 0px 0px 0px rgb(112, 111, 111),
            3px 3px 0px rgb(212, 122, 181);

        color: rgb(212, 122, 181);
        font-weight: bold;
        text-shadow: .5px .5px 0px rgb(212, 122, 181);

        transition: all .2s;
    }

    .b-btn {
        display: flex;
        align-items: center;
        justify-content: center;

        height: 60px;
        width: 60px;
        border-radius: 50%;

        background-color: #C44096;

        transform: rotateZ(-50deg);
        // box-shadow: 3px 3px 0px rgb(252, 171, 162);

        box-shadow: inset 0px 0px 0px rgb(112, 111, 111),
            3px 3px 0px rgb(212, 122, 181);

        color: rgb(212, 122, 181);
        font-weight: bold;
        text-shadow: .5px .5px 0px rgb(212, 122, 181);

        transition: all .2s;
    }

}

.a-b-pressed {
    // box-shadow: 0px 0px 0px rgb(252, 171, 162) !important;

    box-shadow: inset 2px 2px 4px rgb(112, 111, 111),
        0px 0px 0px rgb(252, 171, 162) !important;
}

.d-container {
    display: flex;
    justify-content: center;
    align-items: center;

    height: 180px;
    width: 180px;

    border-radius: 50%;

    box-shadow: inset 5px 5px 10px rgba(0, 0, 0, 0.3);

    perspective: 400px;
}

.d-pad {
    position: relative;
    top: 0;
    left: 0;
    height: 50px;
    width: 50px;
    background-color: rgb(172, 169, 169);

    transition: all 0.2s ease;

    //transform: scale(.5);

    //transform: rotateY(10deg)
}

.clicky-btn {

    position: absolute;
    //top:0px;
    //left: -50px;

    height: 50px;
    width: 50px;
    background-color: rgb(172, 169, 169);
    //border-radius: 10px;
    //box-shadow: inset 3px 3px 0px rgb(204, 202, 202);
    transition: all .2s;

    cursor: pointer;

    display: flex;
    justify-content: center;
    align-items: center;



    // &:active{
    //     box-shadow: 0px 0px 0px rgb(112, 111, 111);
    //     //top: 4px;
    //     // left: 4px;
    // }



    .center-triengle {

        //clip-path: polygon(50% 0%, 0% 100%, 100% 100%);

        height: 20px;
        width: 20px;
        background-color: rgb(189, 186, 186);
        //border-radius: 2px;

        // border-top-left-radius: 50%;
        // border-top-right-radius: 50%;

        box-shadow: inset 2px 2px 3px rgb(112, 111, 111);
        transition: all .2s;



        //transform: rotateZ(45deg);

    }

}



.left {
    top: 0px;
    left: -50px;

    border-top-left-radius: 10px;
    border-bottom-left-radius: 10px;
    //box-shadow: 3px -3px 0px rgb(112, 111, 111); 

    // box-shadow: inset 0px 0px 0px rgb(112, 111, 111);
    box-shadow: inset -4px -4px 0px rgb(187, 186, 186);



    .center-triengle {

        border-top-left-radius: 50%;
        border-bottom-left-radius: 50%;

    }


}

.right {
    top: 0px;
    right: -50px;

    border-top-right-radius: 10px;
    border-bottom-right-radius: 10px;

    // box-shadow: 3px -3px 0px rgb(112, 111, 111);
    //box-shadow: inset 0px 0px 0px rgb(112, 111, 111);

    box-shadow: inset -4px -4px 0px rgb(187, 186, 186);

    .center-triengle {

        border-top-right-radius: 50%;
        border-bottom-right-radius: 50%;

    }
}

.top {
    top: -50px;
    left: 0px;

    border-top-left-radius: 10px;
    border-top-right-radius: 10px;

    // box-shadow: 3px -3px 0px rgb(112, 111, 111);
    // box-shadow: inset 0px 0px 0px rgb(112, 111, 111);
    box-shadow: inset -4px -4px 0px rgb(187, 186, 186);

    .center-triengle {

        border-top-left-radius: 50%;
        border-top-right-radius: 50%;

    }
}

.bottom {
    bottom: -50px;
    left: 0px;

    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;

    // box-shadow: 3px -3px 0px rgb(112, 111, 111);
    // box-shadow: inset 0px 0px 0px rgb(112, 111, 111);
    box-shadow: inset -4px -4px 0px rgb(187, 186, 186);

    .center-triengle {

        border-bottom-left-radius: 50%;
        border-bottom-right-radius: 50%;

    }
}

.d-pad-center {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgb(172, 169, 169);
    transform: scale(1.5); //scale(1.25);

    border-radius: 50%; //10px;

    display: flex;
    justify-content: center;
    align-items: center;

    .center-circle {

        height: 20px;
        width: 20px;
        background-color: rgb(189, 186, 186);
        border-radius: 50%;
        box-shadow: inset 2px 2px 3px rgb(112, 111, 111);
        transition: all .2s;

    }

}

.is-pressed {

    box-shadow: inset 3px 3px 6px rgb(112, 111, 111),
        0px 0px 0px rgb(112, 111, 111);

}

.is-pressed-alt {

    box-shadow: inset -3px 3px 6px rgb(112, 111, 111),
        0px 0px 0px rgb(112, 111, 111);

}
</style>