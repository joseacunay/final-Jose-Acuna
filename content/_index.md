---
title: Welcome to My Creative Hub.
description: xxxxx .
cascade:
  featured_image: "images/f.gif"
---
<!-- Contenedor general para centrar todo -->
<div style="text-align: center;">

  <!-- GIF centrado -->
  <img class="image-top-250" src="/images/tt.gif" alt="Animated GIF">

  <!-- Texto con efecto typing -->
  <div id="typing-text" class="typing-text"></div>
</div>

<style>
/* GIF centrado y tamaño controlado */
.image-top-250 {
    display: block;
    margin: 0 auto 20px auto;
    max-width: 350px;
    height: auto;
}

/* Texto */
.typing-text {
    font-size: 50px;
    font-family: 'Courier New', Courier, monospace;
    line-height: 1.6;
    display: inline-block;
    max-width: 800px;
}

/* Animación de colores */
.typing-letter {
    animation: color-change 4s infinite alternate;
}

@keyframes color-change {
    0% { color: #ff4d4d; }
    25% { color: #4d79ff; }
    50% { color: #4dff88; }
    75% { color: #ffb84d; }
    100% { color: #ff4d4d; }
}
</style>

<script>
const text = `Welcome to my digital space. ;)`;
const container = document.getElementById('typing-text');
let index = 0;

function typeLetter() {
    if(index < text.length){
        let span = document.createElement('span');
        span.className = 'typing-letter';
        span.textContent = text[index];
        container.appendChild(span);
        index++;
        setTimeout(typeLetter, 100);
    } else {
        // Cuando termina de escribir, espera 1 segundo y reinicia
        setTimeout(() => {
            container.innerHTML = ''; // borra el texto
            index = 0;               // reinicia el índice
            typeLetter();            // vuelve a escribir
        }, 1000);
    }
}

// Inicia el efecto
typeLetter();
</script>

# What can you Learn?
<div class="smart-bullets">

  <div class="smart-bullet one">
    ✔️ Educational and interactive guides
  </div>

  <div class="smart-bullet two">
    ✔️ Natural Gas Learning Workshop
  </div>

  <div class="smart-bullet three">
    ✔️ Educational articles about programming
  </div>

</div>

<style>
.smart-bullets {
    position: relative;
    width: 100%;
    height: 200px;
    margin-top: 40px;
}

/* Base de viñetas */
.smart-bullet {
    position: absolute;
    font-size: 26px;
    font-family: 'Courier New', monospace;
    opacity: 0;
    transform: translateY(50px) translateX(0);
    animation: appearMove 1s forwards ease-out;
}

/* Animación combinada: aparecer + moverse */
@keyframes appearMove {
    0% { opacity: 0; transform: translateY(50px) translateX(0); }
    50% { opacity: 1; transform: translateY(0) translateX(0); }
    100% { opacity: 1; transform: translateY(0) translateX(var(--finalX)); }
}

/* Posiciones finales usando CSS variables */
.one {
    --finalX: 0;     /* izquierda */
    left: 120%;
    animation-delay: 0s;
}

.two {
    --finalX: -20%;  /* centro */
    left: 20%;
    animation-delay: 0.5s;
}

.three {
    --finalX: 0;     /* derecha */
    right: 120%;
    animation-delay: 1s;
}
</style>
