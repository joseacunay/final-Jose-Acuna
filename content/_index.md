---
title: Welcome
description: .
src: "/images/joe.jpg"
---

<div style="
    text-align: center;
    background-image: url('{{ .Params.src | absURL }}');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
">

  <!-- GIF centrado -->
  <img class="image-top-250" src="/images/tt.gif" alt="Animated GIF">

  <!-- Texto con efecto typing -->
  <div id="typing-text" class="typing-text"></div>

</div>

<style>
.image-top-250 {
    display: block;
    margin: 0 auto 20px auto;
    max-width: 350px;
    height: auto;
}

.typing-text {
    font-size: 50px;
    font-family: 'Courier New', Courier, monospace;
    line-height: 1.6;
    display: inline-block;
    max-width: 800px;
    color: white;
    text-shadow: 1px 1px 5px rgba(0,0,0,0.7);
}

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
        setTimeout(() => {
            container.innerHTML = '';
            index = 0;
            typeLetter();
        }, 1000);
    }
}

typeLetter();
</script>
