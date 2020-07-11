<template>
  <div class="hello">
    <section>
      <button @click="bounce = !bounce">Bounce</button>
      <br />
      <transition name="bounce">
        <img v-if="bounce" alt="Vue logo" src="../assets/logo.png" />
      </transition>
    </section>

    <section>
      <button @click="flip = !flip">Flip</button>
      <br />
      <transition name="flip">
        <img v-if="flip" alt="Vue logo" src="../assets/logo.png" />
      </transition>
    </section>

    <section>
      <button @click="animated = !animated">Animate</button>
      <br />
      <transition
        name="animate"
        enter-active-class="animate__animated animate__flipInY"
        leave-active-class="animate__animated animate__zoomOutRight"
      >
        <img v-if="animated" alt="Vue logo" src="../assets/logo.png" />
      </transition>
    </section>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      bounce: false,
      flip: false,
      animated: false
    };
  },
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
section {
  min-height: 200px;
  overflow: hidden;
}
.bounce-enter-active {
  animation: bounce-in 0.5s;
}
.bounce-leave-active {
  animation: bounce-in 0.5s reverse;
}

@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}

.flip-enter-active {
  animation: flip-in 0.5s;
}
.flip-leave-active {
  animation: flip-in 0.5s reverse;
}

@keyframes flip-in {
  0% {
    transform: scale(0) rotateZ(0deg) translateX(-250px);
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    transform: scale(1) rotateZ(360deg) translateX(0px);
  }
}
</style>
