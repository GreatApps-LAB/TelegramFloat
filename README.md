# **GreatPages Whatsapp Float**

<a href="https://www.buymeacoffee.com/claitonllemes" target="_blank" rel="noopener noreferrer"><img src="https://user-images.githubusercontent.com/99222756/210368404-216273fb-c930-453e-b32b-e3614872eba3.png" width="100%"/></a><br>

## **Configurações**

Este código é um botão flutuante do Telegram para Greatpages. Possui ícone do Telegram, efeito de pulsação e redireciona o usuário para uma conversa no Telegram. O estilo do botão e ícone é facilmente personalizável através de variáveis CSS. O efeito de pulsação é implementado usando a API Web Animations do JavaScript.

<br><a href="https://www.buymeacoffee.com/claitonllemes" target="_blank" rel="noopener noreferrer"><img src="https://user-images.githubusercontent.com/99222756/210372197-a1d41894-8acc-470b-ac38-2bd1ee0a4ed9.png" width="100%"/></a><br>

```Html
<!-- Telegram Float for Greatpages v. 2.0.0 - Ⓒ Copyright 2023 Claiton Lemes. -->

<a target="_blank" href="SEULINKAQUI" class="float">
  <svg class="icon">
    <path
      d="M0,17.46A3.22,3.22,0,0,1,1.87,16q4.62-1.8,9.26-3.56L42.84.25A3.55,3.55,0,0,1,43.61,0,2,2,0,0,1,46,2.18a17.08,17.08,0,0,1-.45,2.91Q42.3,20.44,39,35.77a6.38,6.38,0,0,1-.53,1.52,1.79,1.79,0,0,1-2.27,1,4.87,4.87,0,0,1-1.36-.65c-3.3-2.39-6.58-4.8-9.87-7.21l-.42-.31c-.13.12-.26.22-.37.33l-5,4.81a2.46,2.46,0,0,1-1.83.75c0-.65.08-1.29.13-1.92.2-2.81.39-5.62.61-8.43a1,1,0,0,1,.3-.59Q27.9,16.42,37.47,7.84s.1-.07.13-.12L38,7.05a2.48,2.48,0,0,0-.82-.14,2.47,2.47,0,0,0-.89.41q-11.9,7.42-23.8,14.87a.85.85,0,0,1-.64.11Q6.73,20.76,1.68,19.17A2.72,2.72,0,0,1,0,18Z" />
  </svg>
</a>

<style>
  :root {
    --icon-color: #ffffff;
    --gradient-normal: #0060ff, #0054db;
    --gradient-hover: #0047ba, #0047ba;
    --pulse-color: #0060ff;
  }

  .icon {
    width: 48px;
    height: 48px;
    transform: scale(0.6) translate(15%, 28%);
    fill: var(--icon-color)
  }

  .float {
    position: fixed;
    cursor: pointer;
    width: 60px;
    height: 60px;
    bottom: 30px;
    right: 30px;
    transition: background 2s;
    background: linear-gradient(45deg, var(--gradient-normal));
    border-radius: 50px;
    z-index: 9000;
  }

  .float:hover {
    background: linear-gradient(45deg, var(--gradient-hover));
  }

  .float:hover .icon {
    fill: var(--icon-color);
  }
</style>

<script>
  const floatBtn = document.querySelector('.float');

  function pulseAnimation() {
    const animation = floatBtn.animate(
      [
        { boxShadow: `0 0 0 0 var(--pulse-color)` },
        { boxShadow: `0 0 0 20px rgba(0, 200, 0, 0)` },
      ],
      {
        duration: 2000,
        easing: 'ease-out',
        iterations: Infinity,
      }
    );

    animation.addEventListener('iteration', (event) => {
      if (event.elapsedTime > 0) {
        floatBtn.style.boxShadow = '0 0 0 0 var(--pulse-color)';
      }
    });
  }

  pulseAnimation();
</script>
```
