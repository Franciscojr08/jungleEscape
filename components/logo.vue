<template>
  <div class="start_game">
    <img src="../static/jungleEscape.png" alt="JungleEscape">
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  text-align: center;
}

.start_game {
    margin: 50px auto 110px auto;
    position: relative;
}

.start_game img {
  max-width: 100%;
}

.start_game {
    animation: movie 20s infinite;
}

@keyframes movie {
    0% {top: 0px}
    10% {top: 100px}
    20% {top: 0px}
    30% {top: 100px}
    40% {top: 0px}
    50% {top: 100px}
    60% {top: 0px}
    70% {top: 100px}
    80% {top: 0px}
    90% {top: 100px}
    100% {top: 0px}
}

</style>
