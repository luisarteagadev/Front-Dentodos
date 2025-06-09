<template>
  <footer>
    <div id="main"><img src="/media/logos/logo_circle.png" alt="" /></div>
    <div id="main">
      <p>Contacto</p>
      <p>Av. de la Policía 505, Jesús María 15072</p>
      <p>correo@gmail.com</p>
      <p>+51 000 000 000</p>
      <p>+51 1 000 0000</p>
    </div>
    <div id="main">
      <p>Horarios</p>
      <p>Lunes a Sábados</p>
      <p>10:00 am - 7:00 pm</p>
    </div>
    <div id="main">
      <p>Síguenos</p>
      <div class="social-icons">
        <a href="#"><img src="/media/icons/facebook.png" alt="Facebook" /></a>
        <a href="#"><img src="/media/icons/instagram.png" alt="Instagram" /></a>
        <a href="#"><img src="/media/icons/linkedin.png" alt="Linkedin" /></a>
      </div>
    </div>
    <div id="copy"><center>&copy; Dentodos 2025</center></div>
  </footer>
</template>

<script></script>

<style lang="scss" scoped>
footer {
  margin: 0;
  padding: 0;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2vw;
  padding: 2vw;
  background-color: var(--color-secondary-1);
  color: white;

  #main {
    display: flex;
    flex-direction: column;
    align-items: flex-start;

    img {
      max-width: 100%;
      margin-bottom: 1vw;
      border-radius: 2vw;
    }

    &:nth-child(1) {
      img {
        display: flex;
        align-self: center;
        width: 10vw;
      }
    }

    p {
      margin: 0.3vw 0;

      &:nth-child(1) {
        font-weight: bold;
      }
    }

    a {
      margin: 0.3vw 0;
    }
  }

  #copy {
    grid-column: 1 / -1; /* Hace que el elemento ocupe todas las columnas */
    font-size: 2.6vw;
    font-weight: bold;
    text-align: center;
    margin-top: 2vw;
  }

  .social-icons {
    display: flex;
    flex-direction: row;
    gap: 1vw;

    a {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 3vw;
      height: 3vw;
      overflow: hidden;
      background-color: var(--color-primary-2);
      border-radius: 50%;

      img {
        display: flex;
        align-self: center;
        justify-self: center;
        margin-top: 0.5vw;
        width: 2vw;
        overflow: hidden;
        filter: invert(1);
        transition: all 250ms;
        margin-bottom: 0;
        border-radius: 0vw;
      }

      &:hover {
        img {
          filter: invert(0);
        }
      }
    }
  }
}
</style>
