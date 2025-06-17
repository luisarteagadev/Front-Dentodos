<template>
  <div class="navigation-component-wrapper">
    <div id="nav-info">
      <div>
        <span class="material-symbols-outlined">
          <q-icon name="call" />
        </span>
        <p>(+51) 932 033 644</p>
      </div>
      <div>
        <div class="social-icons-container">
          <a
            href="https://www.instagram.com/dentodos.peru?utm_source=qr&igsh=MTFubnd6anM5dnVncw=="
            target="_blank"
            ><img src="/media/icons/instagram.png" alt="Instagram"
          /></a>
          <a href="https://www.facebook.com/share/1SidkLWFxN/" target="_blank"
            ><img src="/media/icons/facebook.png" alt="Facebook"
          /></a>
          <a href="https://www.tiktok.com/@dentodos.peru?_t=ZM-8wW8CswOLuq&_r=1" target="_blank"
            ><img src="/media/icons/tiktok.png" alt="Tiktok"
          /></a>
          <a href="https://youtube.com/@dentodosperu9701?si=NaAy9eBRfA7CiwUI" target="_blank"
            ><img src="/media/icons/youtube.png" alt="YouTube"
          /></a>
        </div>
        <a class="appointment-button" @click="$emit('irFormulario')">Separar una cita</a>
      </div>
    </div>
    <!-- :class="{ 'is-sticky-active': isStickyActive }" -->
    <nav ref="navElement">
      <div id="nav-main">
        <div id="logo-img" @click="routerMain()">
          <img src="/media/logos/logo_circle.png" alt="Dentodos" @click="routerMain()" />
        </div>
        <img src="/media/icons/menu_icon.svg" alt="Menú" class="toggle-btn" id="toggleBtn" />
        <div id="nav-options" class="nav-options show">
          <div v-for="linkItem in mainNavLinks" :key="linkItem.label">
            <a @click="goTo(linkItem.href)" v-if="!linkItem.submenu">{{ linkItem.label }}</a>
            <div v-else class="dropdown">
              <a class="dropdown-toggle" :data-label="linkItem.label">
                {{ linkItem.label }}
                <img class="arrow-down" src="/media/icons/arrow_drop_down.svg" />
              </a>
              <div class="dropdown-submenu" :id="'submenu-' + linkItem.label">
                <a
                  v-for="subItem in linkItem.submenu"
                  :key="subItem.label"
                  @click="goTo(subItem.href)"
                >
                  {{ subItem.label }}
                </a>
              </div>
            </div>
          </div>

          <a
            class="options__cotiza"
            href="https://api.whatsapp.com/send?phone=51932033644"
            target="_blank"
            >Cotiza ahora</a
          >
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
      // Toggle menu con JS
      document.getElementById('toggleBtn').addEventListener('click', function () {
        console.log('entre a funcion')
        const navOptions = document.getElementById('nav-options')
        navOptions.classList.toggle('show')
      })
      //      Para mostrar menu de opciones en caso no tenga show
      function handleResize() {
        const navOptions = document.getElementById('nav-options')
        if (window.innerWidth >= 992 && !navOptions.classList.contains('show')) {
          navOptions.classList.add('show')
        }
      }

      window.addEventListener('resize', handleResize)
      window.addEventListener('load', handleResize)

      // Dropdown manual con JS
      const toggles = document.querySelectorAll('.dropdown-toggle')
      toggles.forEach((toggle) => {
        toggle.addEventListener('click', () => {
          console.log('le di click')
          const label = toggle.getAttribute('data-label')
          const submenu = document.getElementById('submenu-' + label)
          console.log('submenu-' + label)
          if (!submenu) return
          const arrow = toggle.querySelector('.arrow-down')
          if (!submenu) return

          submenu.classList.toggle('is-open')
          arrow?.classList.toggle('arrow-rotated')
        })
      })
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

  methods: {
    goTo(href) {
      if (href.startsWith('#')) {
        // scroll dentro de la misma página
        const el = document.querySelector(href)
        if (el) el.scrollIntoView({ behavior: 'smooth' })
      } else {
        // navegación entre rutas
        this.$router.push(href)
      }
    },
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
}
</script>

<style lang="scss" scoped>
@import 'src/css/navigation.scss';
</style>
