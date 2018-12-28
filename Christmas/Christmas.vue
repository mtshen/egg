<template>
  <div class="santa">
    <div class="santa-body">
      <div class="santa-head">
        <div class="santa-ear"></div>
        <div class="santa-ear"></div>
        <div class="santa-hat"></div>
        <div class="santa-eye"></div>
        <div class="santa-eye"></div>
        <div class="santa-nose"></div>
        <div class="santa-mouth"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  created() {
    console.log('%cMerry Christmas ~', 'padding: 10px; font-size: 24px; color: #FFF; background: #f91047');
  },
};
</script>

<style scoped lang="scss">
.santa {
  position: relative;
  display: inline-block;
  vertical-align: middle;
  padding: 15px 8px 0;
  .santa-body {
    font-size: 24px;
    color: #f91047;
    display: flex;
    -webkit-box-pack: center;
    -webkit-justify-content: center;
    -ms-flex-pack: center;
    justify-content: center;
    -webkit-box-align: center;
    -webkit-align-items: center;
    -ms-flex-align: center;
    align-items: center;
    width: 1em;
    height: 1em;
    background-color: currentColor;
    -webkit-box-shadow: inset 0 -0.25em rgba(0,0,0,0.1);
    box-shadow: inset 0 -0.25em rgba(0,0,0,0.1);
    border-radius: 50%;
    transform-origin: center bottom;
    animation: balance alternate infinite 2s ease-in-out;

    .santa-head {
        font-size: .4em;
        width: 1em;
        height: 1.9em;
        background-color: white;
        border-radius: .5em;
        transform: translateY(-1em);
        position: relative;
        &::before {
          content: '';
          width: 1em;
          height: .375em;
          display: block;
          background-color: #ff9876;
          position: absolute;
          left: 0;
          top: .65em;
        }
        .santa-ear:nth-of-type(1) {
          border-radius: .05em 0 0 .05em;
          left: -0.1em;
        }
        .santa-ear:nth-of-type(2) {
          border-radius: 0 .05em .05em 0;
          right: -0.1em;
        }
        .santa-ear {
            background-color: #fc8363;
            width: .1em;
            height: .3em;
            position: absolute;
            top: .75em;
        }
        .santa-hat {
          content: '';
          width: 1em;
          height: .15em;
          position: absolute;
          transform: scale(1.1);
          top: .5em;
          left: 0;
          background-color: white;
          &::before {
            content: '';
            display: block;
            width: 1em;
            height: .5em;
            background: #f91047;
            border-radius: .5em .5em 0 0;
            z-index: 2;
            position: absolute;
            top: -0.5em;
          }
          &::after {
            content: '';
            width: .25em;
            height: .25em;
            display: block;
            background-color: white;
            border-radius: 50%;
            position: absolute;
            z-index: 0;
            top: -0.72em;
            right: 0;
            box-shadow: -0.2em 0.2em 0 0.12em rgba(0,0,0,0.2), -0.2em 0.2em 0 0.12em #f91047;
          }
        }
        .santa-eye {
          width: .12em;
          height: .12em;
          background-color: black;
          border-radius: 50%;
          position: absolute;
          top: .76em;
          left: .2em;
        }
        .santa-eye+.santa-eye {
            left: auto;
            right: .2em;
        }
        .santa-nose {
            width: .12em;
            height: .22em;
            background-color: #f24c4c;
            border-radius: 0 0 .12em .12em;
            position: absolute;
            top: .84em;
            left: 50%;
            transform: translateX(-50%);
        }
        .santa-mouth {
            width: .18em;
            height: .1em;
            border-bottom-right-radius: 5vw;
            border-bottom-left-radius: 5vw;
            margin-top: .3em;
            background-color: black;
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            animation: hohoho 4s linear forwards infinite;
        }
    }
  }
}
@keyframes balance {
  0% {
      -webkit-transform: rotate(-4deg);
      transform: rotate(-4deg);
  }
  100% {
      -webkit-transform: rotate(4deg);
      transform: rotate(4deg);
  }
}
@keyframes hohoho {
  0%, 10%, 20%, 40%, 100% {
      width: .18em;
      height: .1em;
      border-bottom-right-radius: 1vw;
      border-bottom-left-radius: 1vw;
  }
  5%, 15%, 25%, 35% {
      width: .15em;
      height: .2em;
      border-radius: 50%;
  }
}
</style>
