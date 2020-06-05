<div class="gastly">
    <div class="face float">
      <div class="mouth-bottom"></div>
      <div class="mouth-top"></div>
      <div class="right-eye"></div>
      <div class="left-eye"></div>
    </div>
</div>
<svg class="hidden">
  <defs>
    <filter id="smoke">
      <feTurbulence 
        id="turbulence"
        in="SourceGraphic"
        type="fractalNoise"
        baseFrequency="0.025"
        numOctaves="1.5"
        result="TURBULENCE" />
      <feDisplacementMap
        id="displacement"
        in="SourceGraphic"
        in2="TURBULENCE"
        scale="300"
        xChannelSelector="R"
        yChannelSelector="G"
        result="DISPLACEMENT" />
    </filter>
  </defs>
</svg>

<style>
.hidden {
  position: fixed;
  width: 1px;
  height: 1px;
  top: -1px;
  left: -1px;
}

body {
  height: 100vh;
  margin: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: black;
}

.gastly {
    width: 200000%;
    height: 300%;
  border-radius: 50%;
  background-color: black;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: black;
}

.gastly::before {
  content: '';
  width: 400px;
  height: 400px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #8b6283;
  z-index: 500;
  border-radius: 50%;
  filter: url(#smoke);
}

.gastly::after {
  content: '';
  width: 400px;
  height: 400px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #8b6283;
  z-index: 500;
  border-radius: 50%;
  filter: blur(50px);
}

.face {
  width: 300px;
  height: 315px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  border-radius: 50%;
  background-color: #392939;
}

.mouth-bottom {
  position: absolute;
  width: 200px;
  height: 120px;
  top: 68%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #de5239;
  border-radius: 50%;
}

.mouth-bottom::before {
  content: '';
  position: absolute;
  width: 40px;
  height: 40px;
  top: 66%;
  left: 15%;
  transform: translate(-50%, -50%) rotateY(63deg) rotateZ(-47deg);
  border: 1px solid black;
  border-radius: 4px;
  background-color: white;
}

.mouth-bottom::after {
  content: '';
  position: absolute;
  width: 40px;
  height: 40px;
  top: 66%;
  left: 85%;
  transform: translate(-50%, -50%) rotateY(63deg) rotateZ(-47deg);
  border: 1px solid black;
  border-radius: 4px;
  background-color: white;
}

.mouth-top {
  position: absolute;
  width: 250px;
  height: 100px;
  top: 62%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #392939;
  border-radius: 50%;
}

.right-eye {
  width: 155px;
  height: 155px;
  position: absolute;
  top: 57%;
  left: 95%;
  transform: translate(-50%, -50%) rotateZ(55deg) scale(1.2);
  /* border: 1px solid white; */
  border-left: 3px solid black;
  border-top-left-radius: 5% 50%;
  border-bottom-left-radius: 5% 50%;
  overflow: hidden;
}

.right-eye::before {
  content: '';
  width: 115px;
  height: 162px;
  position: absolute;
  top: 50%;
  left: 0%;
  transform: translate(-50%, -50%) rotateZ(125deg);
  border: 1px solid black;
  background-color: white;
  border-radius: 50%;
  box-shadow: inset -22px -15px 0px 0px rgba(0,0,0,0.1);
  background-repeat: no-repeat;
  background-size: 4px 18px;
  background-position: 72% 20%;
  background-image: radial-gradient(black, black 50%, transparent 50%);
}

.left-eye {
  width: 155px;
  height: 160px;
  position: absolute;
  top: 57%;
  left: 5%;
  transform: translate(-50%, -50%) rotateZ(-55deg) scale(1.2);
  border-right: 3px solid black;
  border-top-right-radius: 5% 50%;
  border-bottom-right-radius: 5% 50%;
  overflow: hidden;
}

.left-eye::before {
  content: '';
  width: 115px;
  height: 162px;
  position: absolute;
  top: 50%;
  left: 100%;
  transform: translate(-50%, -50%) rotateZ(-125deg);
  border: 1px solid black;
  background-color: white;
  border-radius: 50%;
  box-shadow: inset -22px -15px 0px 0px rgba(0,0,0,0.1);
  background-repeat: no-repeat;
  background-size: 4px 18px;
  background-position: 27% 20%;
  background-image: radial-gradient(black, black 50%, transparent 50%);
}

.float {
  z-index: 999;
  animation: floating 5s linear infinite;
}

@keyframes floating {
  0% { transform: translate(-50%, -52%) scale(0.8); }
  25% { transform: translate(-50%, -50%) scale(0.81); }
  50% { transform: translate(-50%, -52%) scale(0.8); }
  75% { transform: translate(-50%, -50%) scale(0.81); }
  100% { transform: translate(-50%, -52%) scale(0.8); }
}
</style>



<script>
gsap.to('.gastly', {
  opacity: 0,
  duration: 1,
  
  delay: 7,
  repeatDelay: 7,
  repeat: -1,
  
});

gsap.to('.gastly', {
  opacity: 1,
  duration: 1,
  
  delay: 8,
  repeatDelay: 7,
  repeat: -1,
  
});

gsap.to('#turbulence', {
  duration: 8,
  repeat: -1,
  ease: 'linear',
  attr: {
    baseFrequency: 0.01
  }
});
</script>