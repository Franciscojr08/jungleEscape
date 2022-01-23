<template>
  <div class="game">
    <logo />
    <button class="btn_play">
      <nuxt-link to="/play/1" class="link">
        Iniciar o Jogo
      </nuxt-link>
    </button>
  </div>
</template>

<style>
*{
  margin: 0;
  padding: 0;
}

body {
  background: url(../static/fundoJungle.png) 50%/cover no-repeat;
}

.btn_play {
  border: none;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-weight: bold;
  font-size: 20px;
  color: #000;
  letter-spacing: 1 px;
  outline-style: none;
  padding: 10px;
  border-radius: 10px;
  box-shadow: 2px 2px 10px #000;
  background-color: #F8AE2B;
}

.btn_play:hover, .link:hover {
  cursor: pointer;
  color: #fff;
  transition: all 0.3s ease 0s;
}

.link {
  background-color: transparent;
  text-decoration: none;
  color: #000;
}
</style>
