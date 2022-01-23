<template>
  <div class="game">
    <logoP />
    <h1 class="fase">
      Fase 1
    </h1>

    <p class="pergunta">
      Você acordou na floresta tonto e com uma grande dor de cabeça, sem nenhuma
      memória de como foi parar ali. Um barulho cada vez mais intenso foi o que
      despertou você desse apagão. Após abrir os olhos e levantar-se, você
      observa uma manada de búfalos vindo em sua direção, a pouquíssimos metros
      de distância. O que você faz?
    </p>

    <div class="resposta" @click="abreResposta1()">
      Corre o mais rápido possível
    </div>
    <div class="resposta" @click="abreResposta2()">
      Sobe na árvore
    </div>
    <div class="resposta" @click="abreResposta3()">
      Se finge de morto
    </div>
    <div id="resposta1" class="resposta_e">
      <p>
        A sua corrida não foi suficiente para superar a da manada. Você morreu
        atropelado.
      </p>
      <button class="btn_play_game">
        <nuxt-link to="/" class="link_game">
          Início do Jogo
        </nuxt-link>
      </button>
    </div>
    <div id="resposta2" class="resposta_v">
      <p>
        Você sobe na árvore e escapa por pouco da manada.
      </p>
      <button class="btn_play_game">
        <nuxt-link to="/play/2" class="link_game">
          Próxima fase
        </nuxt-link>
      </button>
    </div>
    <div id="resposta3" class="resposta_e">
      <p>
        Os búfalos podem até ter acreditado, mas isso não os impediu de passar
        por cima de você. Morreu atropelado.
      </p>
      <button class="btn_play_game">
        <nuxt-link to="/" class="link_game">
          Início do Jogo
        </nuxt-link>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      contagem1: 0,
      contagem2: 0,
      contagem3: 0,
      abreResposta1: () => {
        if (this.contagem2 === 0 && this.contagem3 === 0) {
          document.getElementById('resposta1').style.display = 'block'
          this.contagem1++
        } else if (this.contagem1 >= 1) {
          alert('Volte para o início do jogo!'); location.href = '../'
        } else {
          document.getElementById('resposta1').style.display = 'none'
          this.contagem1++
        }
      },
      abreResposta2: () => {
        if (this.contagem1 === 0 && this.contagem3 === 0) {
          document.getElementById('resposta2').style.display = 'block'
          this.contagem2++
        } else if (this.contagem2 >= 1) {
          alert('Volte para o início do jogo!'); location.href = '../'
        } else {
          document.getElementById('resposta2').style.display = 'none'
          this.contagem2++
        }
      },
      abreResposta3: () => {
        if (this.contagem1 === 0 && this.contagem2 === 0) {
          document.getElementById('resposta3').style.display = 'block'
          this.contagem3++
        } else if (this.contagem3 >= 1) {
          alert('Volte para o início do jogo!'); location.href = '../'
        } else {
          document.getElementById('resposta3').style.display = 'none'
          this.contagem3++
        }
      }
    }
  }
}
</script>

<style>

*{
  margin: 0;
  padding: 0;
}

body {
  background: url(../../static/fundoJungle.png) 50%/cover no-repeat;
}

.game{
  width: 50%;
  margin: 20px auto;
}

.fase {
  text-align: center;
  color: #F8AE2B;
}

.pergunta {
  margin: 15px auto;
  text-align: justify;
  color: #000;
  letter-spacing: 1px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.resposta {
  padding: 10px;
  border: none;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-size: 18px;
  font-weight: bold;
  color: #000;
}

.resposta:hover {
  cursor: pointer;
  color: #F8AE2B;
  text-decoration: underline;
}

.resposta_e {
  margin: 25px auto;
  text-align: justify;
  color: #ff0000;
  font-weight: bold;
  letter-spacing: 1px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  display: none;
  text-align: center;
}

.resposta_v {
  margin: 25px auto;
  text-align: justify;
  color: #0000ff;
  font-weight: bold;
  letter-spacing: 1px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  display: none;
  text-align: center;
}

.btn_play_game {
  margin: 25px auto;
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

.btn_play_game:hover, .link_game:hover {
  cursor: pointer;
  color: #fff;
  transition: all 0.3s ease 0s;
}

.link_game {
  background-color: transparent;
  text-decoration: none;
  color: #000;
}

</style>
