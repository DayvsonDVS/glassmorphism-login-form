<template>
  <section>
    <div class="leaves">
      <div class="set">
        <div v-for="i in 4">
          <img :src="`/images/leaf_0${i}.png`" />
        </div>

        <div v-for="i in 4">
          <img :src="`/images/leaf_0${i}.png`" />
        </div>
      </div>
    </div>

    <img src="@/images/bg.jpg" class="bg" />
    <img src="@/images/girl.png" class="girl" />
    <img src="@/images/trees.png" class="trees" />

    <div class="login">
      <h2>Sign In</h2>
      <div class="inputBox">
        <input type="text" placeholder="Username" />
      </div>

      <div class="inputBox">
        <input type="password" placeholder="Password" />
      </div>

      <div class="inputBox">
        <input type="submit" value="Login" id="btn" />
      </div>

      <div class="group">
        <a href="">Forgot Password</a>
        <a href="">Signup</a>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import '@/assets/scss/main.scss'
</script>

<style scoped lang="scss">
section {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
  overflow: hidden;
  .leaves {
    position: absolute;
    width: 100%;
    height: 100vh;
    overflow: hidden;
    display: flex;
    justify-content: center;
    z-index: 1;
    pointer-events: none;
    .set {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      pointer-events: none;
      div {
        position: absolute;
        display: block;
        &:nth-child(1) {
          left: 20%;
          animation: animate 20s linear infinite;
        }
        &:nth-child(2) {
          left: 50%;
          animation: animate 14s linear infinite;
        }
        &:nth-child(3) {
          left: 70%;
          animation: animate 12s linear infinite;
        }
        &:nth-child(4) {
          left: 5%;
          animation: animate 15s linear infinite;
        }
        &:nth-child(5) {
          left: 85%;
          animation: animate 18s linear infinite;
        }
        &:nth-child(6) {
          left: 90%;
          animation: animate 12s linear infinite;
        }
        &:nth-child(7) {
          left: 15%;
          animation: animate 14s linear infinite;
        }
        &:nth-child(8) {
          left: 60%;
          animation: animate 15s linear infinite;
        }

        @keyframes animate {
          0% {
            opacity: 0;
            top: -10%;
            transform: translateX(20px) rotate(0deg);
          }
          10% {
            opacity: 1;
          }
          20% {
            transform: translateX(-20px) rotate(45deg);
          }
          40% {
            transform: translateX(-20px) rotate(90deg);
          }
          60% {
            transform: translateX(20px) rotate(180deg);
          }
          80% {
            transform: translateX(-20px) rotate(45deg);
          }
          100% {
            top: 110%;
            transform: translateX(20px) rotate(225deg);
          }
        }
      }
    }
  }
  .bg {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    pointer-events: none;
  }
  .girl {
    position: absolute;
    scale: 0.65;
    animation: animateGirl 10s linear infinite;
    pointer-events: none;
  }
  @keyframes animateGirl {
    0% {
      transform: translateX(calc(100% + 100vw));
    }
    50% {
      transform: translateX(calc(-100% - 100vw));
    }
    50.01% {
      transform: translateX(calc(-100% - 100vw)) rotateY(180deg);
    }
    100% {
      transform: translateX(calc(100% + 100vw)) rotateY(180deg);
    }
  }
  .trees {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: 100;
    pointer-events: none;
  }
  .login {
    position: relative;
    padding: 60px;
    background: rgba(255, 255, 255, 0.25);
    backdrop-filter: blur(15px);
    border: 1px solid #fff;
    border-bottom: 1px solid rgba(255, 255, 255, 0.5);
    border-right: 1px solid rgba(255, 255, 255, 0.5);
    border-radius: 20px;
    width: 500px;
    display: flex;
    flex-direction: column;
    gap: 30px;
    box-shadow: 0 25px 50px rgba(0, 0, 0, 0.1);
    h2 {
      position: relative;
      width: 100%;
      text-align: center;
      font-size: 2.5em;
      font-weight: 600;
      color: #8f2c24;
      margin-bottom: 10px;
    }
    .inputBox {
      position: relative;
      ::placeholder {
        color: #8f2c24;
      }
      input {
        position: relative;
        width: 100%;
        padding: 15px 20px;
        outline: none;
        font-size: 1.25em;
        color: #8f2c24;
        border-radius: 5px;
        background: #fff;
        border: none;
      }
      #btn {
        position: relative;
        border: none;
        background: #8f2c24;
        color: #fff;
        font-size: 1.25em;
        font-weight: 500;
        transition: 0.5s;
        cursor: pointer;
        &:hover {
          background: #d64c42;
        }
      }
    }
    .group {
      display: flex;
      justify-content: space-between;
      a {
        font-size: 1.25em;
        color: #8f2c24;
        font-weight: 500;
        text-decoration: none;
        &:nth-child(2) {
          text-decoration: underline;
        }
      }
    }
  }
}
</style>
