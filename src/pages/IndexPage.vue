<template>
  <q-page>
    <!-- <div class="caja-con-video-fondo">
      <video autoplay loop muted playsinline>
        <source :src="videoHomeSrc" type="video/mp4" />
        Tu navegador no soporta la reproducción de video.
      </video>
      <div class="mascara-video"></div>
    </div> -->

    <NavigationBar
      :mainNavLinks="navigationMenuItems"
      @irFormulario="scrollToFormulario"
      style="position: absolute"
    />

    <div id="body">
      <div id="presentation">
        <video id="video-hero" autoplay muted loop playsinline>
          <source :src="videoHomeSrc" type="video/mp4" />
          Tu navegador no soporta video HTML5.
        </video>
        <div class="content">
          <p class="title">Dentodos, pensando en todos, donde cada sonrisa importa.</p>
          <p class="description">
            Perfeccionamos tu salud bucal en manos expertas, con una atención personalizada
            comprometida con tu bienestar.
          </p>
          <a class="btn-call-action" @click="scrollToFormulario">
            <p class="text-call-action">Reserva tu cita</p>
            <img class="icon-call-action" src="/media/icons/next.png" alt="" />
          </a>
        </div>
      </div>

      <div id="services">
        <div id="s-title">
          <p>Nuestros Servicios</p>
          <p class="title-service">Soluciones dentales oportunas para cada necesidad</p>
          <p>
            Ofrecemos una experiencia dental confiable, cercana y adaptada a tus expectativas, con
            un enfoque integral para que sonrías con confianza.
          </p>
        </div>

        <div id="services-cards-enterprise-2">
          <div class="card">
            <div class="c-bg-color">
              <div class="card-icon">
                <img src="/media/icons/med-exam.png" alt="" />
              </div>
              <div class="card-text">
                <p class="ct-title">Diseño de Sonrisa</p>
                <p class="ct-desc">
                  Transforma la apariencia, color y tamaño de tus dientes. <q-space /> Lúcete con
                  una sonrisa radiante, natural y hecha a tu medida.
                </p>
              </div>
              <a @click="routerIntegrales()">
                <p>Ver Más</p>
                <img src="/media/icons/next.png" alt="" />
              </a>
            </div>
          </div>
          <div class="card">
            <div class="c-bg-color">
              <div class="card-icon">
                <img src="/media/icons/med-enterprise.png" alt="" />
              </div>
              <div class="card-text">
                <p class="ct-title">Atención Dental 24 horas</p>
                <p class="ct-desc">
                  Atención dental diurna y nocturna los 7 días de la semana. <q-space /> Acude a
                  nosotros con tranquilidad, estamos disponibles cuando más lo necesitas.
                </p>
              </div>
              <a @click="scrollToFormulario()">
                <p>Separar una cita</p>
                <img src="/media/icons/next.png" alt="" />
              </a>
            </div>
          </div>
          <div class="card">
            <div class="c-bg-color">
              <div class="card-icon">
                <img src="/media/icons/med-campain.png" alt="" />
              </div>
              <div class="card-text">
                <p class="ct-title">Servicio a domicilio</p>
                <p class="ct-desc">
                  Dentista cerca de ti sin salir de casa. <q-space /> Atención profesional en la
                  comodidad de tu hogar, porque tu bienestar no depende de la distancia.
                </p>
              </div>
              <a @click="scrollToFormulario()">
                <p>Separar una cita</p>
                <img src="/media/icons/next.png" alt="" />
              </a>
            </div>
          </div>
          <div class="card">
            <div class="c-bg-color">
              <div class="card-icon">
                <img src="/media/icons/med-ocupational.png" alt="" />
              </div>
              <div class="card-text">
                <p class="ct-title">Ortodoncia</p>
                <p class="ct-desc">
                  Consigue una sonrisa alineada y saludable.<q-space /> Recupera tu confianza y
                  disfruta de una sonrisa que refleje tu mejor versión.
                </p>
              </div>
              <a @click="scrollToFormulario()">
                <p>Separar una cita</p>
                <img src="/media/icons/next.png" alt="" />
              </a>
            </div>
          </div>
        </div>
        <div id="container-tratamientos">
          <div id="s-title">
            <p>Nuestros Tratamientos</p>
            <p>Descubre nuestra gama de tratamientos por especialidad.</p>
            <p></p>
          </div>
          <div id="services-cards-personal">
            <!-- <div class="card" @click="routerIntegrales()"> -->
            <div class="card">
              <div class="card-content">
                <span>Integrales</span>
                <p>
                  El primer paso hacia una sonrisa sana.<q-space /> Ideal para prevenir, corregir y
                  preparar tu boca antes de cualquier tratamiento, con un enfoque en tu bienestar.
                </p>
              </div>
            </div>
            <div class="card">
              <div class="card-content">
                <span>Rehabilitación</span>
                <p>
                  Restaura la estética y funcionalidad de tu sonrisa mediante tratamientos como
                  coronas, puentes y prótesis. <q-space />Mejora tu capacidad para masticar, hablar
                  y sonreír con confianza.
                </p>
              </div>
            </div>
            <div class="card">
              <div class="card-content">
                <span>Periodoncia e Implantes</span>
                <p>
                  Recupera la salud de tus encías y reemplaza los dientes perdidos con implantes de
                  calidad. <q-space />Logra una sonrisa completa y duradera.
                </p>
              </div>
            </div>
            <div class="card">
              <div class="card-content">
                <span>Endodoncia</span>
                <p>
                  Alivia el dolor y salva tus dientes dañados, evitando la extracción.
                  <q-space />Limpiando la raíz de tu diente de manera rápida y efectiva.
                </p>
              </div>
            </div>
            <div class="card">
              <div class="card-content">
                <span>Cirugía Oral / Maxilofacial</span>
                <p>
                  Soluciones quirúrgicas para corregir problemas de la boca, mandíbula y rostro, con
                  resultados precisos.
                </p>
              </div>
            </div>
            <div class="card">
              <div class="card-content">
                <span>Odontopediatría</span>
                <p>
                  Cuidamos la salud dental de los más pequeños, con un enfoque cálido, preventivo y
                  divertido, creando experiencias positivas desde la primera visita y acompañándolos
                  en cada etapa de su desarrollo.
                </p>
              </div>
            </div>
          </div>
        </div>

        <div id="s-title">
          <p></p>
          <p>Ofertas</p>
          <p>Descuentos especiales, pensados para cuidar tu sonrisa y tu bolsillo.</p>
        </div>

        <div id="tarj_price">
          <div class="card">
            <!-- <p class="sub-text">Ofertas especiales</p> -->
            <p class="main-text">¡Tu limpieza dental con 30% menos! Haz clic y aprovecha.</p>
            <a href="https://api.whatsapp.com/send?phone=51932033644" target="_blank">
              <p>Comprar</p>
              <img src="/media/icons/next.png" alt="" />
            </a>
          </div>
          <div class="card">
            <p class="main-text">
              Cupón de S/ 30 soles de descuento, válido para compras desde S/150 soles.
            </p>
            <a href="https://api.whatsapp.com/send?phone=51932033644" target="_blank">
              <p>Comprar</p>
              <img src="/media/icons/next.png" alt="" />
            </a>
          </div>
          <div class="card">
            <p class="main-text">¡Instalación de brackets brasileros a S/600 soles!</p>
            <a href="https://api.whatsapp.com/send?phone=51932033644" target="_blank">
              <p>Comprar</p>
              <img src="/media/icons/next.png" alt="" />
            </a>
          </div>
        </div>
      </div>

      <div id="personal">
        <div id="s-title">
          <p>NUESTRO EQUIPO</p>
          <p>Un equipo de expertos capacitados y comprometidos con tu bienestar.</p>
        </div>

        <div id="pro-team">
          <div class="q-pa-md">
            <q-carousel
              v-model="slide"
              transition-prev="slide-right"
              transition-next="slide-left"
              swipeable
              animated
              :autoplay="autoplay"
              control-color="amber"
              navigation
              infinite
              padding
              arrows
              height="auto"
            >
              <q-carousel-slide :name="1" class="column no-wrap">
                <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
                  <div id="pro-card-container">
                    <div class="card">
                      <div class="img-pro">
                        <img
                          src="/media/photos/ESPECIALISTAS/DR. ANGEL CAVALIÉ (ESTÉTICA).png"
                          alt=""
                        />
                      </div>
                      <p class="pro-name">Dr. Angel Cavalié</p>
                      <p class="pro-COP">COP 35804</p>
                      <p class="pro-area">Estética</p>
                      <p class="pro-desc" v-if="pro_view">
                        "Lo que busco es que tu sonrisa sea el mejor reflejo de ti, realzando lo que
                        ya te hace único."
                      </p>
                      <a @click="pro_view = !pro_view">Ver más</a>
                    </div>
                    <div class="card">
                      <div class="img-pro">
                        <img
                          class="img-pro--carla"
                          src="/media/photos/ESPECIALISTAS/DRA. CARLA GRANADOS (INTEGRALES).png"
                          alt=""
                        />
                      </div>
                      <p class="pro-name">Dra. Carla Granados</p>
                      <p class="pro-COP">COP 35814</p>
                      <p class="pro-area">Intregrales</p>
                      <p class="pro-desc" v-if="pro_view">
                        "Creo que la mejor sonrisa es la que se construye paso a paso y con
                        paciencia."
                      </p>
                      <a @click="pro_view = !pro_view">Ver más</a>
                    </div>
                    <div class="card">
                      <div class="img-pro">
                        <img
                          src="/media/photos/ESPECIALISTAS/DRA. CELESTE TELLO (ORTODONCIA).png"
                          alt=""
                        />
                      </div>
                      <p class="pro-name">Dra. Celeste Tello</p>
                      <p class="pro-COP">COP 43343</p>
                      <p class="pro-area">Ortodoncia</p>
                      <p class="pro-desc" v-if="pro_view">
                        "Fan de los cambios visibles, me encanta ver sonrisas transformarse en cada
                        sesión."
                      </p>
                      <a @click="pro_view = !pro_view">Ver más</a>
                    </div>

                    <div class="card">
                      <div class="img-pro">
                        <img
                          src="/media/photos/ESPECIALISTAS/DR. DIEGO ABARCA (CIRUGÍA ORAL).png"
                          alt=""
                        />
                      </div>
                      <p class="pro-name">Dr. Diego Abarca</p>
                      <p class="pro-COP">COP 37678</p>
                      <p class="pro-area">Cirugía Oral</p>
                      <p class="pro-desc" v-if="pro_view">
                        "Lo mío es trabajar con precisión para hacer cada cirugía lo más cómoda
                        posible."
                      </p>
                      <a @click="pro_view = !pro_view">Ver más</a>
                    </div>
                  </div>
                </div>
              </q-carousel-slide>
              <q-carousel-slide :name="2" class="column no-wrap">
                <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
                  <div id="pro-card-container">
                    <div class="card">
                      <div class="img-pro">
                        <img
                          src="/media/photos/ESPECIALISTAS/DRA. DIANA LESCANO (ENDODONCIA).png"
                          alt=""
                        />
                      </div>
                      <p class="pro-name">Dra. Diana Lescano</p>
                      <p class="pro-COP">COP 36032</p>
                      <p class="pro-area">Endodoncia</p>
                      <p class="pro-desc" v-if="pro_view">
                        "Cada raíz tiene su historia y me encanta darle un final feliz, porque todo
                        diente merece ser salvado."
                      </p>
                      <a @click="pro_view = !pro_view">Ver más</a>
                    </div>
                    <div class="card">
                      <div class="img-pro">
                        <img
                          src="/media/photos/ESPECIALISTAS/DRA. RUTH BALLASCO (INTEGRALES).png"
                          alt=""
                        />
                      </div>
                      <p class="pro-name">Dra. Ruth Ballasco</p>
                      <p class="pro-COP"></p>
                      <p class="pro-area">Integrales</p>
                      <p class="pro-desc" v-if="pro_view">
                        "Toda sonrisa restaurada es una forma de atender con propósito, creando
                        resultados duraderos."
                      </p>
                      <a @click="pro_view = !pro_view">Ver más</a>
                    </div>
                    <div class="card">
                      <div class="img-pro">
                        <img
                          src="/media/photos/ESPECIALISTAS/DRA. INGRID SOTELO (REHABILITACIÓN).png"
                          alt=""
                        />
                      </div>
                      <p class="pro-name">Dra. Ingrid Sotelo</p>
                      <p class="pro-COP">COP 37398</p>
                      <p class="pro-area">Rehabilitación Oral</p>
                      <p class="pro-desc" v-if="pro_view">
                        "Convencida de que una sonrisa completa transforma vidas. Mi objetivo es que
                        cada paciente sonría con libertad y sin preocupaciones"
                      </p>
                      <a @click="pro_view = !pro_view">Ver más</a>
                    </div>
                  </div>
                </div>
              </q-carousel-slide>
            </q-carousel>
          </div>
        </div>
      </div>

      <div id="testimonials">
        <div id="s-title">
          <p>Testimonios</p>
        </div>

        <div class="carousel-container">
          <div id="pro-team">
            <div class="q-pa-md">
              <q-carousel
                v-model="slide2"
                transition-prev="slide-right"
                transition-next="slide-left"
                swipeable
                animated
                :autoplay="autoplay"
                control-color="amber"
                navigation
                infinite
                padding
                arrows
                height="auto"
              >
                <!-- Video 1 -->
                <q-carousel-slide :name="3">
                  <div>
                    <video class="video-testimonial" controls>
                      <source :src="testimonio1" type="video/mp4" />
                      Tu navegador no soporta el video.
                    </video>
                  </div>
                </q-carousel-slide>

                <!-- Video 2 -->
                <q-carousel-slide :name="4">
                  <div class="">
                    <video class="video-testimonial" controls>
                      <source :src="testimonio2" type="video/mp4" />
                      Tu navegador no soporta el video.
                    </video>
                  </div>
                </q-carousel-slide>

                <!-- Video 3 -->
                <q-carousel-slide :name="5">
                  <div class="">
                    <video class="video-testimonial" controls>
                      <source :src="testimonio3" type="video/mp4" />
                      Tu navegador no soporta el video.
                    </video>
                  </div>
                </q-carousel-slide>
              </q-carousel>
            </div>
          </div>
          <!-- <div class="carousel-track" ref="carouselTrackRef">
            <div class="carousel-slide">
              <video
                width="560"
                height="315"
                controls
                :src="testimonio1"
                title="Video de testimonio"
              >
                Tu navegador no soporta el video HTML5.
              </video>
            </div>
            <div class="carousel-slide">
              <video
                width="560"
                height="315"
                controls
                :src="testimonio2"
                title="Video de testimonio"
              >
                Tu navegador no soporta el video HTML5.
              </video>
            </div>
            <div class="carousel-slide">
              <video
                width="560"
                height="315"
                controls
                :src="testimonio3"
                title="Video de testimonio"
              >
                Tu navegador no soporta el video HTML5.
              </video>
            </div>
          </div>


          <button class="carousel-button prev" aria-label="Video anterior" ref="prevButtonRef">
            &lt;
          </button>
          <button class="carousel-button next" aria-label="Siguiente video" ref="nextButtonRef">
            &gt;
          </button>
          <div class="carousel-nav" ref="navDotsContainerRef"></div> -->
        </div>
      </div>
    </div>

    <MapAndForm />

    <div class="go-top-container" v-show="showButton">
      <div class="go-top-button" @click="scrollToTop">
        <img src="/media/icons/arrow_top.svg" alt="Subir al inicio" />
      </div>
    </div>

    <EndFooter />
  </q-page>
</template>

<script>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import NavigationBar from 'src/components/Navigation/NavegationBar.vue'
import MapAndForm from 'src/components/MapForm.vue'
import EndFooter from 'src/components/EndFooter.vue'
import { VIDEOS } from '../constants'

export default {
  components: { NavigationBar, MapAndForm, EndFooter },
  data() {
    return {
      showButton: false,
      videoHomeSrc: VIDEOS.videoHome,
      testimonio1: VIDEOS.testimonio1,
      testimonio2: VIDEOS.testimonio2,
      testimonio3: VIDEOS.testimonio3,
    }
  },
  mounted() {
    // Cuando el componente se monta, se agrega un "escuchador" al scroll
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeUnmount() {
    // Limpieza del escuchador cuando el componente se elimina
    window.removeEventListener('scroll', this.handleScroll)
  },
  setup() {
    // --- INICIO: Lógica del Carrusel de Testimonios (YouTube) ---
    const carouselTrackRef = ref(null)
    const nextButtonRef = ref(null)
    const prevButtonRef = ref(null)
    const navDotsContainerRef = ref(null)

    let ytSlides = [] // Renombrado para evitar confusión con 'slide' del q-carousel
    let ytNavDots = [] // Renombrado
    let ytCurrentSlideIndex = 0 // Renombrado
    const ytStepVw = 45 // vw por slide para el carrusel de YouTube

    const stopCurrentYouTubeVideo = () => {
      if (ytSlides.length === 0 || !ytSlides[ytCurrentSlideIndex]) return
      const currentSlideElement = ytSlides[ytCurrentSlideIndex]
      const iframe = currentSlideElement.querySelector('iframe')
      if (iframe?.contentWindow) {
        iframe.contentWindow.postMessage('{"event":"command","func":"stopVideo","args":""}', '*')
      }
    }

    const updateYouTubeNavButtons = () => {
      if (!prevButtonRef.value || !nextButtonRef.value) return
      prevButtonRef.value.style.display = ytCurrentSlideIndex === 0 ? 'none' : 'block'
      nextButtonRef.value.style.display =
        ytCurrentSlideIndex >= ytSlides.length - 1 ? 'none' : 'block'
    }

    const moveToYouTubeSlide = (targetIndex) => {
      if (!carouselTrackRef.value || targetIndex < 0 || targetIndex >= ytSlides.length) return
      stopCurrentYouTubeVideo()
      const offsetVw = ytStepVw * targetIndex
      carouselTrackRef.value.style.transform = `translateX(-${offsetVw}vw)`

      if (navDotsContainerRef.value && ytNavDots.length > 0) {
        const currentActiveDot = navDotsContainerRef.value.querySelector('.nav-dot.active')
        if (currentActiveDot) {
          currentActiveDot.classList.remove('active')
        }
        if (ytNavDots[targetIndex]) {
          ytNavDots[targetIndex].classList.add('active')
        }
      }
      ytCurrentSlideIndex = targetIndex
      updateYouTubeNavButtons()
    }

    const handleYouTubeNext = () => {
      const nextIndex = ytCurrentSlideIndex + 1
      if (nextIndex < ytSlides.length) {
        moveToYouTubeSlide(nextIndex)
      }
    }

    const handleYouTubePrev = () => {
      const prevIndex = ytCurrentSlideIndex - 1
      if (prevIndex >= 0) {
        moveToYouTubeSlide(prevIndex)
      }
    }

    const handleYouTubeResize = () => {
      if (!carouselTrackRef.value) return
      const offsetVw = ytStepVw * ytCurrentSlideIndex
      carouselTrackRef.value.style.transition = 'none'
      carouselTrackRef.value.style.transform = `translateX(-${offsetVw}vw)`
      setTimeout(() => {
        if (carouselTrackRef.value) {
          carouselTrackRef.value.style.transition = 'transform 0.5s ease-in-out'
        }
      }, 50)
    }

    onMounted(() => {
      // Inicialización del carrusel de YouTube
      const track = carouselTrackRef.value
      const nextButton = nextButtonRef.value
      const prevButton = prevButtonRef.value
      const navDotsContainer = navDotsContainerRef.value

      if (track) {
        ytSlides = Array.from(track.children).filter((child) =>
          child.classList.contains('carousel-slide'),
        )
        if (ytSlides.length > 0 && nextButton && prevButton) {
          if (navDotsContainer) {
            ytSlides.forEach((s, index) => {
              // 's' para evitar conflicto con 'slide' global
              const dot = document.createElement('button')
              dot.classList.add('nav-dot')
              if (index === 0) dot.classList.add('active')
              const dotClickListener = () => moveToYouTubeSlide(index)
              dot.addEventListener('click', dotClickListener)
              dot._ytClickListener = dotClickListener // Guardar referencia
              navDotsContainer.appendChild(dot)
            })
            ytNavDots = Array.from(navDotsContainer.children)
          }
          nextButton.addEventListener('click', handleYouTubeNext)
          prevButton.addEventListener('click', handleYouTubePrev)
          updateYouTubeNavButtons()
          window.addEventListener('resize', handleYouTubeResize)
          moveToYouTubeSlide(0) // Asegurar posición inicial
        } else if (ytSlides.length === 0) {
          console.warn('IndexPage: No slides found for YouTube carousel.')
        } else if (!nextButton || !prevButton) {
          console.warn('IndexPage: Navigation buttons not found for YouTube carousel.')
        }
      } else {
        console.warn("IndexPage: YouTube carousel track (ref='carouselTrackRef') not found.")
      }
    })

    onBeforeUnmount(() => {
      // Limpieza del carrusel de YouTube
      if (nextButtonRef.value) nextButtonRef.value.removeEventListener('click', handleYouTubeNext)
      if (prevButtonRef.value) prevButtonRef.value.removeEventListener('click', handleYouTubePrev)
      ytNavDots.forEach((dot) => {
        if (dot._ytClickListener) dot.removeEventListener('click', dot._ytClickListener)
      })
      ytNavDots = []
      window.removeEventListener('resize', handleYouTubeResize)
    })
    // --- FIN: Lógica del Carrusel de Testimonios (YouTube) ---

    return {
      slide: ref(1),
      autoplay: ref(true),
      pro_view: ref(false),
      slide2: ref(1),
      navigationMenuItems: ref([
        { label: 'Home', href: '/' }, // Puedes usar Vue Router paths aquí
        {
          label: 'Servicios',
          submenu: [
            { label: 'Diseño de sonrisa', href: '/TInte' },
            { label: 'Servicio a domicilio', href: '#services-cards-personal' },
            { label: 'Ortodoncia', href: '#tarj_price' },
          ],
        },
        { label: 'Tratamientos', href: '#services-cards-personal' },
        { label: 'Ofertas', href: '#tarj_price' }, // Enlace a una sección de la misma página
        { label: 'Equipo', href: '#personal' },
        { label: 'Testimonios', href: '#testimonials' }, // Otro enlace a sección
        {
          label: 'Pacientes',
          href: '#reviews',
        },
      ]),
      // Referencias para el carrusel de YouTube (necesarias para el template)
      carouselTrackRef,
      nextButtonRef,
      prevButtonRef,
      navDotsContainerRef,
    }
  },
  methods: {
    scrollToFormulario() {
      const el = document.getElementById('forms')
      if (el) {
        el.scrollIntoView({ behavior: 'smooth' })
      }
    },
    scrollToProTeam() {
      this.pro_view.value = true // Asumiendo que pro_view es un ref
      // Opcional: Scroll suave a la sección
      const element = document.getElementById('pro-team')
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' })
      }
    },
    handleScroll() {
      // Si el usuario ha hecho scroll más de 200px, muestra el botón
      this.showButton = window.scrollY > 200
    },
    scrollToTop() {
      // Scroll suave hacia la parte superior de la página
      window.scrollTo({
        top: 0,
        behavior: 'smooth',
      })
    },
    routerIntegrales() {
      this.$router.push('TInte')
    },
  },
}
</script>
<style lang="scss" scoped>
@import 'src/css/indexpage.scss';
</style>
