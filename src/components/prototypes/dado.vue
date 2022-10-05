<template>
    <div class="container-dado column bg-[#dbbb7e] py-24">

        <div class="stage">
            <div class="cube animacion-giro">
                <div 
                    v-for="(side, i) in sides" 
                    :class="[
                        'grid place-content-center side rounded-2xl',
                        side
                    ]">

                    <div  class="h-12 w-12 bg-white rounded-full inner-dado border-2 border-black"></div>


                    </div>
                <!-- <div class="flex justify-center items-center side s-top border-2 rounded-2xl"></div>
                <div class="flex justify-center items-center side s-bottom border-2 rounded-2xl"></div>
                <div class="flex justify-center items-center side s-left border-2 rounded-2xl"></div>
                <div class="flex justify-center items-center side s-right border-2 rounded-2xl"></div>
                <div class="flex justify-center items-center side s-front border-2 rounded-2xl"></div> -->
            </div>
        </div>

    </div>
</template>

<script setup lang="ts">

    let sides = ['s-back', 's-top', 's-bottom', 's-left', 's-right', 's-front']

</script>

<style scoped lang="scss">

.inner-dado{
    box-shadow: inset 10px 10px 8px rgba($color: #000000, $alpha: 0.4);
}

.container-dado{
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
    width: 100%;

    perspective: 400px; // para que el efecto 3d tenga efectos
}

.column{
  flex-direction: column;
  gap: 150px;
}

@keyframes gira-dado{
  from{
    transform: rotateY(30deg) rotateX(10deg);
  }
  
  to{
    transform: rotateY(390deg) rotateX(10deg);
  }
}

.animacion-giro{
  
  animation: gira-dado infinite 3s linear;
  
}


$c-height: 200px;
$c-width: 200px;

.stage{
    width: $c-width;
    height: $c-height;

    perspective: 1600px;
    perspective-origin: 50% -240px;

}

.cube { 
    transform-style: preserve-3d; 
    transform: rotateY(30deg);
    transform-origin: center;
    

    // animation-name: card-rotation-back;
    // animation-duration: 8s;
    // animation-iteration-count: infinite;

}

.side{
    position: absolute;
    height: $c-height;
    width: $c-width;
    background-color: rgba(96, 194, 239, 0.6);
  
    //border: 1px solid black;

    transform-origin: 50% 50% 0;
  
    //backdrop-filter: blur(4px);
}


.s-front { transform: translateZ(calc($c-width / 2)); }
.s-back { transform: rotateY(180deg) translateZ(calc($c-width / 2)); }

.s-top { 

    transform: rotateX(90deg) translateZ(calc($c-height / 2));

    background-color: rgba(187, 255, 0, 0.6);
    
}
.s-bottom {
    
    transform: rotateX(-90deg) translateZ(calc($c-height / 2)); 
    
    background-color: rgba(255, 0, 0, 0.6);

}

.s-left { 
    transform: rotateY(-90deg) translateZ(calc($c-width / 2)); 
    background-color: rgba(0, 128, 0,0.6);
}
.s-right { 
    transform: rotateY(90deg) translateZ(calc($c-width / 2)); 
    background-color: rgba(0, 0, 255, 0.6);
}



</style>