<template>
  <div class="navigation-component-wrapper">
    <div id="nav-info">
      <div>
        <span class="material-symbols-outlined">
          <q-icon name="call" />
        </span>
        <p>(+51) 999 888 777</p>
      </div>
      <div>
        <div class="social-icons-container">
          <a href="#"><img src="/media/icons/linkedin.png" alt="Linkedin" /></a>
          <a href="#"><img src="/media/icons/facebook.png" alt="Facebook" /></a>
          <a href="#"><img src="/media/icons/instagram.png" alt="Instagram" /></a>
          <a href="#"><img src="/media/icons/youtube.png" alt="YouTube" /></a>
        </div>
        <p class="appointment-button">Separar una cita</p>
      </div>
    </div>

    <nav ref="navElement" :class="{ 'is-sticky-active': isStickyActive }">
      <div id="nav-main">
        <div id="logo-img" @click="routerMain()">
          <img src="/media/logos/logo_circle.png" alt="Dentodos" @click="routerMain()" />
        </div>
        <div id="nav-options">
          <a
            v-for="linkItem in mainNavLinks"
            :key="linkItem.label"
            @click="scrollToElement(linkItem.href)"
          >
            {{ linkItem.label }}
          </a>

          <a href="#">Cotiza ahora</a>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
import { ref, onMounted, onBeforeUnmount } from 'vue'

export default {
  props: {
    mainNavLinks: {
      type: Array,
      default: () => [], // Por defecto, un array vacío si no se proveen enlaces
      // Cada objeto en el array debería tener una estructura como: { label: 'Texto del Enlace', href: '/ruta' }
    },
  },
  methods: {
    scrollToElement(elementId) {
      const element = document.getElementById(elementId)
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' })

        // Opcionalmente, si usas Quasar y quieres más control o integración:
        // import { scroll } from 'quasar';
        // const { getScrollTarget, setVerticalScrollPosition } = scroll;
        // const target = getScrollTarget(element);
        // const offset = element.offsetTop; // O una lógica de offset más precisa
        // const duration = 500; // en milisegundos
        // setVerticalScrollPosition(target, offset, duration);
      } else {
        console.warn(`Elemento con ID '${elementId}' no encontrado para hacer scroll.`)
      }
    },
    routerMain() {
      this.$router.push('/')
    },
  },
  setup() {
    // 'props' ahora está disponible aquí
    const navElement = ref(null)
    const isStickyActive = ref(false)
    let observer = null

    onMounted(() => {
      if (!navElement.value) {
        console.error(
          'NavigationBar: Elemento <nav> no encontrado. Asegúrate de que \'ref="navElement"\' esté en el tag <nav>.',
        )
        return
      }
      // ... (Tu lógica del IntersectionObserver sigue aquí igual) ...
      // Ejemplo de la lógica del observer que tenías:
      observer = new IntersectionObserver(
        ([entry]) => {
          const topThreshold = 1 // O el umbral que prefieras (e.g., 5)
          if (entry.boundingClientRect.top <= topThreshold) {
            if (!isStickyActive.value) isStickyActive.value = true
          } else {
            if (isStickyActive.value) isStickyActive.value = false
          }
        },
        {
          threshold: [0, 0.05, 0.95, 1.0],
        },
      )
      observer.observe(navElement.value)
    })

    onBeforeUnmount(() => {
      if (observer && navElement.value) {
        observer.unobserve(navElement.value)
      }
      observer = null
    })

    // No necesitas retornar 'mainNavLinks' desde setup,
    // la plantilla puede acceder a las props directamente.
    return {
      navElement,
      isStickyActive,
    }
  },
}
</script>

<style lang="scss" scoped>
/* Contenedor principal del componente */
.navigation-component-wrapper {
  /* Puedes añadir un fondo aquí si #nav-info no debe ser transparente sobre el video directamente */
  /* background-color: var(--color-primary-3-low); */ /* Ejemplo */
  margin-top: 0.5vw;
  position: relative;
  z-index: 1000;

  /* NAV-INFO STYLES (Barra superior) */
  #nav-info {
    display: flex;
    align-items: start;
    flex-direction: column;
    background-color: transparent;
    color: white;
    font-weight: bold;
    margin: 1vw 5vw;
    padding-bottom: 0;
    font-weight: normal;
    overflow: visible;
    gap: 1vw;
    z-index: 1000;
    transition: all 400ms;

    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 89vw;
    background-color: transparent;
    height: 1.5vw;
    flex-direction: row;

    // border: 1px solid red;

    div {
      &:nth-child(1) {
        display: flex;
        align-items: center;
        flex-direction: row;
        gap: 0.5vw;
        font-size: 0.75vw;

        .material-symbols-outlined {
          /* Material icons size */
          font-size: 0.75vw;
          color: var(--color-primary-1);
        }

        p {
          color: var(--color-secondary-2);
          font-weight: bold;
          margin: 0;
        }
      }

      &:nth-child(2) {
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 1vw;

        div {
          gap: 0.5vw;

          a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 2vw;
            height: 2vw;
            overflow: hidden;
            background-color: var(--color-primary-1);
            border-radius: 50%;

            img {
              align-self: center;
              justify-self: center;
              width: 1vw;
              overflow: hidden;
              filter: invert(1);
            }
          }
        }

        p {
          font-size: 0.75vw;
          background-color: var(--color-primary-1);
          padding: 0.5vw 1.5vw;
          border-radius: 9999px;
          margin: 0;
        }
      }
    }
  }

  /* NAV-MAIN STYLES (Barra inferior) */

  nav {
    position: sticky;
    top: 0;
    display: flex;
    align-items: start;
    flex-direction: column;
    background-color: transparent;
    color: white;
    font-weight: bold;
    padding: 1vw 5vw;
    font-weight: normal;
    overflow: visible;
    z-index: 1000;
    transition: all 400ms;
    /* background-color: var(--color-primary-1-low); */

    #nav-main {
      // border: 1px solid red;
      box-shadow: -13px 10px 15px -3px rgba(0, 0, 0, 0.1);
      display: flex;
      align-items: center;
      justify-content: space-between;
      background-color: var(--color-primary-3);
      width: 100%;
      box-sizing: border-box;
      height: 5vw;
      padding: 0 1vw;
      color: black;
      border-radius: 2vw;
      font-weight: bold;
      overflow: hidden;
      z-index: 100;

      .is-sticky {
        /* Modifications to apply when sticky */
        box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2); /* Example: Change box shadow */
        background-color: var(--color-primary-2); /* Example: Change background color */
        height: 4vw; /* Example: Change height */
        padding: 0.5vw 1vw; /* Example: Adjust padding */
      }

      #logo-img {
        cursor: pointer;
        img {
          width: 4.5vw;
        }
      }

      #nav-options {
        display: flex;
        align-items: center;
        flex-direction: row;
        gap: 1.5vw;
        margin: 0 1vw;

        a {
          padding: 1.5vw 0;
          font-size: 1vw;
          color: black;
          text-decoration: none;
          transition: all 250ms;
          cursor: pointer;

          &:hover {
            font-size: 1vw;
            color: var(--color-primary-1);
            text-decoration-line: underline;
            text-decoration-color: var(--color-primary-1);
            text-decoration-thickness: 0.25vw;
            text-underline-offset: 0.5vw;
            /* text-decoration: none; */
          }

          &:last-child {
            color: white;
            background-color: var(--color-primary-1);
            padding: 0.75vw 2vw;
            border-radius: 9999px;
            text-decoration: none;
          }
        }
      }
    }
  }
}
</style>
