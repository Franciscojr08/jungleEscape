<template>
  <div class="game">
    <logoP />
    <h1 class="fase">
      Última Fase
    </h1>

    <p class="pergunta">
      Você finalmente consegue ler o bilhete: “Vamos fazer parecer um acidente. Misture o
      conteúdo deste frasco na comida dele. O remédio vai começar a fazer efeito depois
      de 30 minutos. Quando ele estiver completamente apagado, leve-o até o pé da
      árvore mais alta no início da floresta e direcione a manada de búfalos em sua
      direção. Estaremos esperando no laboratório ao norte do acampamento.” O que
      você faz?
    </p>

    <div class="resposta" @click="abreResposta1()">
      Foge e liga para a polícia
    </div>
    <div class="resposta" @click="abreResposta2()">
      Amarra o homem e vai ao laboratório
    </div>
    <div class="resposta" @click="abreResposta3()">
      Mata o homem, pega a marreta e vai ao laboratório
    </div>
    <div id="resposta1" class="resposta_v">
      <p>
        Você informa a polícia o que aconteceu e passa a localização do
        laboratório. Chegando lá ela se depara com um sítio de produção de cocaína
        e prende todos os presentes. As evidências sugerem que você ainda pode
        estar em perigo, por este motivo a polícia lhe coloca no programa de
        proteção à testemunha e você sobrevive para vivenciar uma nova história.
        Parabéns, você ganhou!
      </p>
      <button class="btn_play_game">
        <nuxt-link to="/" class="link_game">
          Você Venceu
        </nuxt-link>
      </button>
    </div>
    <div id="resposta2" class="resposta_e">
      <p>
        Você amarra o homem e se dirige ao laboratório. Você entra
        silenciosamente e consegue chegar ao salão principal, onde você observa
        aproximadamente umas 10 pessoas. Um passo em falso entrega a sua
        posição e você é alvejado. Você morreu.
      </p>
      <button class="btn_play_game">
        <nuxt-link to="/" class="link_game">
          Início do Jogo
        </nuxt-link>
      </button>
    </div>
    <div id="resposta3" class="resposta_e">
      <p>
        Você mata o homem, pega a marreta e se dirige ao laboratório. Ao avistar
        2 guardas na entrada, confiante de si e seus feitos recentes, você corre na
        direção dos guardas, segurando a marreta com as duas mãos levantadas
        acima da sua cabeça e gritando “LEEROY JEENKINS!!!!”. Infelizmente, o
        efeito surpresa foi prejudicado e os guardas não tiveram dificuldade em
        alvejá-lo. Você morreu.
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

<style scoped>

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
  color: #008000;
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
