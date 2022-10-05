<template>
    <div class="container-figma bg-[#EDDDBF] py-24 grid place-content-center grid-rows-1">
    
    <div class="figma-logo relative col-start-1 row-start-1 origin-center z-10 drop-shadow-lg">
        <div class="col1">
        <div class="ball no-b-r bg-white scale-125"></div>
        <div class="ball no-b-r bg-white scale-125"></div>
        <div class="ball no-b-t-r bg-white scale-125"></div>
        </div>
        
        <div class="col1">
        <div class="ball no-b-l bg-white scale-125"></div>
        <div class="ball bg-white scale-125"></div>
        
        </div>

        <div class="absolute x-position shadow-pin -top-12 bg-[#EDDDBF] border-8 border-white h-12 w-12 rounded-full"></div>
        
    </div>

    <div class="figma-logo col-start-1 row-start-1 z-20">
        <div class="col1">
        <div class="ball no-b-r orange"></div>
        <div class="ball no-b-r purple"></div>
        <div class="ball no-b-t-r green"></div>
        </div>
        
        <div class="col1">
        <div class="ball no-b-l pink"></div>
        <div class="ball blue"></div>
        
        </div>
        
    </div>

    
    
    </div>
</template>

<style scoped lang="scss">

.container-figma{
//   display: flex;
//   justify-content: center;
//   align-items: center;
//   flex-direction: column;
  height: 100%;
  width: 100%;
  
  
}

.x-position{
    left: calc(50% - 1.5rem);
}

.shadow-pin{
    box-shadow: inset 5px 5px 10px rgba(0,0,0,0.3);
}

.lite-text{
  color: #0a9396;
}

.ball{
  height: 100px;
  width: 100px;
  
  border-radius: 50%;
}

.no-b-r{
  border-top-right-radius: 0px;
  border-bottom-right-radius: 0px;
}

.no-b-l{
  border-top-left-radius: 0px;
  border-bottom-left-radius: 0px;
}

.no-b-t-r{
  border-top-right-radius: 0px;
  
}

.orange{
  background-color: #F24E1E;
}

.purple{
  background-color: #A259FF;
}

.green{
  background-color: #0ACF83;
}

.pink{
  background-color: #FF7262;
}

.blue{
  background-color: #1ABCFE;
}

.figma-logo{
  display: flex;
 
}

</style>