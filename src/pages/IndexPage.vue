<template>
  <q-page>
    <div class="caja-con-video-fondo">
      <video autoplay loop muted playsinline>
        <!-- <source src="/media/videos/4489831-hd_1280_720_50fps.mp4" type="video/mp4" />
          -->
        <source :src="videoHomeSrc" type="video/mp4" />
        Tu navegador no soporta la reproducción de video.
      </video>
      <div class="mascara-video"></div>
    </div>

    <NavigationBar :mainNavLinks="navigationMenuItems" style="position: sticky" />

    <div id="body">
      <div id="presentation">
        <p>Dentodos, pensado en todos, donde cada sonrisa importa.</p>
        <p>
          Perfeccionamos tu salud bucal en manos expertas, con una atención personalizada
          comprometida con tu bienestar.
        </p>
        <a href="#">
          <p>Reserva tu cita</p>
          <img src="/media/icons/next.png" alt="" />
        </a>
      </div>

      <div id="services">
        <div id="s-title">
          <p>Nuestros Servicios</p>
          <p>Soluciones dentales oportunas para cada necesidad</p>
          <p>
            Ofrecemos una experiencia dental confiable, cercana y adaptada a tus expectativas, con
            un enfoque integral para que sonrías con confianza.
          </p>
        </div>

        <div id="services-cards-enterprise-2">
          <div class="card" @click="routerIntegrales()">
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
              <a href="#">
                <p>Separar una cita</p>
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
              <a href="#">
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
              <a href="#">
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
              <a href="#">
                <p>Separar una cita</p>
                <img src="/media/icons/next.png" alt="" />
              </a>
            </div>
          </div>
        </div>
        <div id="container-tratamientos">
          <div id="s-title">
            <p>NUESTROS TRATAMIENTOS</p>
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
          <p>OFERTAS</p>
          <p>Descuentos especiales, pensadas para cuidar tu sonrisa y tu bolsillo.</p>
        </div>

        <div id="tarj_price">
          <div class="card">
            <p class="sub-text">Ofertas especiales</p>
            <p class="main-text">¡Tu limpieza dental con 30% menos! Haz clic y aprovecha.</p>
            <a href="#">
              <p>Comprar</p>
              <img src="/media/icons/next.png" alt="" />
            </a>
          </div>
          <div class="card">
            <p class="sub-text">Ofertas especiales</p>
            <p class="main-text">
              Cupón de S/ 30 soles de descuento, válido para compras desde S/150 soles.
            </p>
            <a href="#">
              <p>Comprar</p>
              <img src="/media/icons/next.png" alt="" />
            </a>
          </div>
          <div class="card">
            <p class="sub-text">Ofertas especiales</p>
            <p class="main-text">¡Instalación de brackets brasileros a S/600 soles!</p>
            <a href="#">
              <p>Comprar</p>
              <img src="/media/icons/next.png" alt="" />
            </a>
          </div>
        </div>
      </div>

      <div id="testimonials">
        <div id="s-title">
          <p>Testimonios de nuestra calidad de servicio</p>
        </div>

        <div class="carousel-container">
          <div class="carousel-track" ref="carouselTrackRef">
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

          <!-- <div class="carousel-nav"></div> -->

          <button class="carousel-button prev" aria-label="Video anterior" ref="prevButtonRef">
            &lt;
          </button>
          <button class="carousel-button next" aria-label="Siguiente video" ref="nextButtonRef">
            &gt;
          </button>
          <div class="carousel-nav" ref="navDotsContainerRef"></div>
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
              control-color="amber"
              navigation
              infinite
              :autoplay="autoplay"
              padding
              arrows
              height="30vw"
              class="bg-white-9"
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
                      <p class="pro-COP">COP -</p>
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
        <!-- <div id="pro-container">
          <div id="pro-card">
            <div id="pro-image">
              <img src="/media/photos/pro-photo-1.webp" alt="" />
            </div>
            <div id="pro-desc">
              <p id="pro-name">Dra. Juana Pérez</p>
              <p id="pro-title">Odontóloga</p>
              <p id="pro-full-text">
                Con más de 10 años de experiencia en el campo de la odontología, la Dra. Pérez es un
                experto en ortodoncia y estética dental.
              </p>
              <div id="pro-redes">
                <div>
                  <a href="#">
                    <img src="/media/icons/linkedin.png" alt="Linkedin" />
                  </a>
                  <a href="#">
                    <img src="/media/icons/facebook.png" alt="Linkedin" />
                  </a>
                  <a href="#">
                    <img src="/media/icons/instagram.png" alt="Linkedin" />
                  </a>
                </div>
                <a href="#" id="contact">Contact me</a>
              </div>
            </div>
          </div>
          <div id="pro-card">
            <div id="pro-image">
              <img src="/media/photos/pro-photo-1.webp" alt="" />
            </div>
            <div id="pro-desc">
              <p id="pro-name">Dra. Juana Pérez</p>
              <p id="pro-title">Odontóloga</p>
              <p id="pro-full-text">
                Con más de 10 años de experiencia en el campo de la odontología, la Dra. Pérez es un
                experto en ortodoncia y estética dental.
              </p>
              <div id="pro-redes">
                <div>
                  <a href="#">
                    <img src="/media/icons/linkedin.png" alt="Linkedin" />
                  </a>
                  <a href="#">
                    <img src="/media/icons/facebook.png" alt="Linkedin" />
                  </a>
                  <a href="#">
                    <img src="/media/icons/instagram.png" alt="Linkedin" />
                  </a>
                </div>
                <a href="#" id="contact">Contact me</a>
              </div>
            </div>
          </div>
          <div id="pro-card">
            <div id="pro-image">
              <img src="/media/photos/pro-photo-1.webp" alt="" />
            </div>
            <div id="pro-desc">
              <p id="pro-name">Dra. Juana Pérez</p>
              <p id="pro-title">Odontóloga</p>
              <p id="pro-full-text">
                Con más de 10 años de experiencia en el campo de la odontología, la Dra. Pérez es un
                experto en ortodoncia y estética dental.
              </p>
              <div id="pro-redes">
                <div>
                  <a href="#">
                    <img src="/media/icons/linkedin.png" alt="Linkedin" />
                  </a>
                  <a href="#">
                    <img src="/media/icons/facebook.png" alt="Linkedin" />
                  </a>
                  <a href="#">
                    <img src="/media/icons/instagram.png" alt="Linkedin" />
                  </a>
                </div>
                <a href="#" id="contact">Contact me</a>
              </div>
            </div>
          </div>
          <div id="pro-card">
            <div id="pro-image">
              <img src="/media/photos/pro-photo-1.webp" alt="" />
            </div>
            <div id="pro-desc">
              <p id="pro-name">Dra. Juana Pérez</p>
              <p id="pro-title">Odontóloga</p>
              <p id="pro-full-text">
                Con más de 10 años de experiencia en el campo de la odontología, la Dra. Pérez es un
                experto en ortodoncia y estética dental.
              </p>
              <div id="pro-redes">
                <div>
                  <a href="#">
                    <img src="/media/icons/linkedin.png" alt="Linkedin" />
                  </a>
                  <a href="#">
                    <img src="/media/icons/facebook.png" alt="Linkedin" />
                  </a>
                  <a href="#">
                    <img src="/media/icons/instagram.png" alt="Linkedin" />
                  </a>
                </div>
                <a href="#" id="contact">Contact me</a>
              </div>
            </div>
          </div>
          <div id="pro-card">
            <div id="pro-image">
              <img src="/media/photos/pro-photo-1.webp" alt="" />
            </div>
            <div id="pro-desc">
              <p id="pro-name">Dra. Juana Pérez</p>
              <p id="pro-title">Odontóloga</p>
              <p id="pro-full-text">
                Con más de 10 años de experiencia en el campo de la odontología, la Dra. Pérez es un
                experto en ortodoncia y estética dental.
              </p>
              <div id="pro-redes">
                <div>
                  <a href="#">
                    <img src="/media/icons/linkedin.png" alt="Linkedin" />
                  </a>
                  <a href="#">
                    <img src="/media/icons/facebook.png" alt="Linkedin" />
                  </a>
                  <a href="#">
                    <img src="/media/icons/instagram.png" alt="Linkedin" />
                  </a>
                </div>
                <a href="#" id="contact">Contact me</a>
              </div>
            </div>
          </div>
          <div id="pro-card">
            <div id="pro-image">
              <img src="/media/photos/pro-photo-1.webp" alt="" />
            </div>
            <div id="pro-desc">
              <p id="pro-name">Dra. Juana Pérez</p>
              <p id="pro-title">Odontóloga</p>
              <p id="pro-full-text">
                Con más de 10 años de experiencia en el campo de la odontología, la Dra. Pérez es un
                experto en ortodoncia y estética dental.
              </p>
              <div id="pro-redes">
                <div>
                  <a href="#">
                    <img src="/media/icons/linkedin.png" alt="Linkedin" />
                  </a>
                  <a href="#">
                    <img src="/media/icons/facebook.png" alt="Linkedin" />
                  </a>
                  <a href="#">
                    <img src="/media/icons/instagram.png" alt="Linkedin" />
                  </a>
                </div>
                <a href="#" id="contact">Contact me</a>
              </div>
            </div>
          </div>
        </div> -->
      </div>
    </div>

    <MapAndForm />

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
      videoHomeSrc: VIDEOS.videoHome,
      testimonio1: VIDEOS.testimonio1,
      testimonio2: VIDEOS.testimonio2,
      testimonio3: VIDEOS.testimonio3,
    }
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
      navigationMenuItems: ref([
        { label: 'Home', href: '/' }, // Puedes usar Vue Router paths aquí
        { label: 'Servicios Top', href: 'services' },
        { label: 'Tratamientos', href: 'services-cards-personal' },
        { label: 'Ofertas', href: 'tarj_price' }, // Enlace a una sección de la misma página
        { label: 'Testimonios', href: 'testimonials' },
        { label: 'Nuestro Equipo', href: 'personal' }, // Otro enlace a sección
        {
          label: 'Reseñas Google',
          href: 'reviews',
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
    scrollToProTeam() {
      this.pro_view.value = true // Asumiendo que pro_view es un ref
      // Opcional: Scroll suave a la sección
      const element = document.getElementById('pro-team')
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' })
      }
    },
    routerIntegrales() {
      this.$router.push('TInte')
    },
  },
}
</script>

<style lang="scss" scoped>
q-page {
  width: 100vw;
  height: 100vw;
  border: 1px solid red;
}

* {
  font-family: 'Gotham Rounded', Arial, sans-serif;
}
// UTILIDADES
.bg-secondary-section {
  background-color: #e8e8e8;
}

/* VIDEO DE FONDO*/

.caja-con-video-fondo {
  position: absolute;
  width: 99vw;
  height: 56vw;
  overflow: hidden;
  margin: -1.25vw 0;
  padding: 0;
  z-index: -1;

  video {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);

    min-width: 100%;
    min-height: 50vw;
    width: auto;
    height: auto;

    max-width: 99vw;
    z-index: -2;
    display: block;
  }

  .mascara-video {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 56vw;
    background-color: var(--color-primary-1-low);
    z-index: -1;
  }
}

/* BODY */

#body {
  /* border: 1px solid red; */
  position: relative;
  margin: 1vw 5vw;
  height: auto;
  z-index: 1;

  nav {
    position: sticky;
  }

  #presentation {
    display: flex;
    /* align-items: center; */
    flex-direction: column;
    /* border: 1px solid green; */
    margin: 10vw 30vw 15vw 0vw;
    padding: 2vw 2vw 2vw 0vw;
    /* background-color: var(--color-secondary-1-medium); */
    color: white;
    gap: 1vw;

    p {
      &:nth-child(1) {
        font-size: 3vw;
        font-weight: bold;
      }

      &:nth-child(2) {
        font-size: 2vw;
        font-weight: normal;
        margin-bottom: 1vw;
      }
    }

    a {
      display: flex;
      flex-direction: row;
      font-weight: bold;
      justify-self: start;
      align-items: center;
      justify-content: space-between;
      padding: 1vw;
      width: 15vw;
      color: black;
      border-radius: 9999px;
      transition: all 250ms;
      border: none;
      background-color: var(--color-primary-3);
      text-decoration: none;

      p {
        display: flex;
        justify-self: center;
        align-self: center;
        margin: 0;
        &:nth-child(1) {
          font-size: 1vw;
          font-weight: bold;
        }
      }

      img {
        width: 2vw;
        margin-right: 1vw;
        transition: all 250ms;
      }

      &:hover {
        color: #e8e8e8;
        background-color: var(--color-primary-1);

        img {
          filter: invert(1);
          margin: 0;
        }
      }
    }
  }

  #services {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    gap: 3vw;

    #container-tratamientos {
      padding: 16px 0px;
      border-radius: 16px;
      background: linear-gradient(to right, #e8e8e8 75%, #ffffff);
    }
    #s-title {
      display: flex;
      flex-direction: column;
      gap: 1vw;

      p {
        &:nth-child(1) {
          font-size: 1.5vw;
          font-weight: bold;
          color: var(--color-primary-1);
        }

        &:nth-child(2) {
          font-size: 2vw;
          font-weight: bold;
          color: var(--color-secondary-1);
        }

        &:nth-child(3) {
          font-weight: normal;
          font-size: 1.5vw;

          span {
            font-weight: bold;
            color: var(--color-primary-1);
          }
        }
      }
    }

    #services-cards-enterprise-2 {
      display: flex;
      gap: 1vw;

      .card {
        background-color: var(--color-primary-1-low);
        height: 25vw;
        width: 20vw;
        flex: 1;
        border-radius: 1vw;
        transition: all 0.3s ease;
        display: flex;
        align-items: center;
        justify-content: center;
        overflow: hidden;
        position: relative;
        transition: all 250ms;

        .c-bg-color {
          width: 100%;
          height: 100%;
          transition: all 250ms;
        }

        .card-icon {
          position: absolute;
          top: 1vw;
          left: 1vw;
          overflow: hidden;
          height: 5vw;
          width: 5vw;
          border-radius: 50%;
          display: flex;
          align-items: center;
          justify-content: center;
          background-color: var(--color-primary-2);
          transition: all 250ms;

          img {
            width: 3vw;
            filter: invert(1);
          }
        }

        a {
          display: flex;
          flex-direction: row;
          font-family: 'Gotham Rounded', Arial, sans-serif;
          justify-content: space-between;
          margin-left: 1vw;
          padding: 1vw;
          width: 15vw;
          color: white;
          border-radius: 1vw;
          transition: all 250ms;
          border: none;
          background-color: var(--color-primary-1);
          position: absolute;
          bottom: 1vw;
          opacity: 0;
          left: 1vw;
          text-decoration: none;

          p {
            &:nth-child(1) {
              all: unset;
              display: flex;
              align-self: center;
              color: white;
              font-size: 1vw;
              font-weight: bold;
            }
          }

          img {
            width: 2vw;
            margin-right: 1vw;
            filter: invert(1);
          }
        }

        &:nth-child(1) {
          background-image: url('/media/photos/SERVICIOS/DISEÑO DE SONRISA.JPG');
          background-size: cover;
          background-position: center;
          background-repeat: no-repeat;
        }

        &:nth-child(2) {
          background-image: url('/media/photos/SERVICIOS/ATENCIÓN DENTAL 24 HRS.jpeg');
          background-size: cover;
          background-position: center;
          background-repeat: no-repeat;
        }

        &:nth-child(3) {
          background-image: url('/media/photos/SERVICIOS/SERVICIO A DOMICILIO.jpeg');
          background-size: cover;
          background-position: center;
          background-repeat: no-repeat;
        }

        &:nth-child(4) {
          background-image: url('/media/photos/med-exam.jpg');
          background-size: cover;
          background-position: center;
          background-repeat: no-repeat;
        }

        &:hover {
          .c-bg-color {
            width: 100%;
            height: 100%;
            background-color: var(--color-secondary-1-medium);
          }

          .card-icon {
            background-color: var(--color-secondary-1);
            top: 1vw;
            left: calc(15vw / 2);
          }

          .card-text {
            all: unset;
            position: absolute;
            text-align: center;
            padding: 0 1vw;
            width: 80%;
            top: 8vw;
            left: 50%;
            transform: translate(-50%);
            height: min-content;

            .ct-title {
              text-align: center;
              justify-self: center;
              color: white;
              width: 90%;
              padding: 0.5vw;
              border-bottom: 0.2vw solid white;
              margin-bottom: 1vw;
            }

            .ct-desc {
              all: unset;
              text-align: center;
              color: white;

              &:not(:empty) {
                position: initial;
                text-align: start;
                font-weight: normal;
                font-size: 0.75vw;
                opacity: 1;
              }
            }
          }

          a {
            opacity: 1;
          }
        }
      }

      .card-text {
        padding: 1vw;
        font-size: 1vw;
        background-color: var(--color-primary-2);
        text-align: start;
        border-radius: 1vw;
        margin: 0 1vw;
        color: white;
        font-weight: bold;
        position: absolute;
        bottom: 1vw;
        left: 0vw;
        transition: all 250ms;

        .ct-title {
          font-size: 1vw;
          font-weight: bold;
          text-align: start;
          transition: all 250ms;
        }

        .ct-desc {
          font-size: 0.05vw;
          font-weight: bold;
          text-align: start;
          position: absolute;
          bottom: 1vw;
          left: 1vw;
          opacity: 0;
          transition: all ease-in 250ms;
        }
      }
    }

    #services-cards-personal {
      width: 90vw;
      display: grid;
      grid-template-columns: calc(84vw / 3) calc(84vw / 3) calc(84vw / 3);
      grid-template-rows: 17vw 17vw;
      column-gap: 2vw;
      row-gap: 1vw;
      padding: 0vw 2vw;

      .card {
        display: flex;
        align-self: center;
        justify-self: center;
        width: 25vw;
        height: 15vw;
        background: rgb(103, 225, 255);
        transition: all 0.4s;
        border-radius: 2vw;
        box-shadow: 12px 17px 51px rgba(0, 0, 0, 0.22);
        font-size: 30px;
        font-weight: 900;
        /* z-index: -2; */
        overflow: hidden;

        .card-content {
          display: flex;
          align-self: flex-end;
          justify-self: center;
          height: 5vw;
          width: 25vw;
          padding: 0 1vw;
          background-color: var(--color-primary-1-medium);
          transition: all 0.4s;
          justify-content: start;
          align-items: center;
          position: relative;

          span {
            position: absolute;
            top: 1.5vw;
            color: white;
            font-size: 1.5vw;
            opacity: 1;
          }

          p {
            position: absolute;
            top: 3.5vw;
            color: white;
            font-size: 0.7vw;
            margin: 0 1vw 0 0;
            font-weight: normal;
            text-align: justify;
            opacity: 0;
          }
        }

        &:hover {
          border-radius: 2vw;
          cursor: pointer;
          transform: scale(1.1);
          box-shadow: 12px 17px 51px rgba(0, 0, 0, 0.22);

          .card-content {
            height: 8vw;
            background-color: var(--color-primary-1);

            span {
              top: 1vw;
            }

            p {
              opacity: 1;
            }
          }
        }

        &:nth-child(1) {
          background-image: url('/media/photos/TRATAMIENTOS/INTEGRALES.jpeg');
          background-size: cover;
          background-position: center;
          background-repeat: no-repeat;
        }

        &:nth-child(2) {
          background-image: url('/media/photos/TRATAMIENTOS/REHABILITACIÓN.jpeg');
          background-size: cover;
          background-position: center;
          background-repeat: no-repeat;
        }

        &:nth-child(3) {
          background-image: url('/media/photos/TRATAMIENTOS/PERIODONCIA E IMPLANTES.jpeg');
          background-size: cover;
          background-position: center;
          background-repeat: no-repeat;
        }

        &:nth-child(4) {
          background-image: url('/media/photos/TRATAMIENTOS/ENDODONCIA.jpeg');
          background-size: cover;
          background-position: center;
          background-repeat: no-repeat;
        }

        &:nth-child(5) {
          background-image: url('/media/photos/TRATAMIENTOS/CIRUGÍA ORAL _ MAXILOFACIAL.jpeg');
          background-size: cover;
          background-position: center;
          background-repeat: no-repeat;
        }

        &:nth-child(6) {
          background-image: url('/media/photos/TRATAMIENTOS/ODONTOPEDIATRÍA.jpeg');
          background-size: cover;
          background-position: center;
          background-repeat: no-repeat;
        }
      }
    }

    #tarj_price {
      margin: 0 6vw;
      width: 100%;
      gap: 3vw;
      display: flex;
      flex-direction: row;
      margin-bottom: 2vw;
      // border: 1px solid red;

      .card {
        flex: 1;
        height: 18vw;
        padding: 2vw;
        position: relative;
        border-radius: 1vw;
        background-image: linear-gradient(
          to bottom right,
          var(--color-primary-1) 50%,
          var(--color-primary-2) 100%
        );
        transition: all 250ms;
        display: flex;
        flex-direction: column;
        justify-content: space-between;

        box-shadow: 1.5vw 1.4vw 0.75vw -0.7vw rgba(0, 0, 0, 0.1);

        p {
          color: white;
          text-align: start;
        }

        .sub-text {
          font-weight: normal;
          font-size: 1vw;
        }

        .main-text {
          font-weight: bold;
          font-size: 1.5vw;
        }

        a {
          // position: absolute;
          // bottom: 2vw;
          // left: 2vw;
          width: 12vw;
          display: flex;
          align-items: center;
          justify-content: space-between;
          padding: 0.5vw 1.5vw 0.5vw 0.5vw;
          background-color: white;
          flex-direction: row;
          text-decoration: none;
          font-weight: bold;
          border-radius: 0.5vw;
          transition: all 250ms;

          p {
            color: black;
            letter-spacing: 0.05vw;
          }

          img {
            width: 2vw;
          }

          &:hover {
            padding: 0.5vw;
            background-color: var(--color-primary-2);

            p {
              color: white;
            }

            img {
              filter: invert(1);
            }
          }
        }

        &:hover {
          transform: scale(1.1);
        }
      }
    }
  }

  #testimonials {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    gap: 3vw;
    margin-top: 2vw;
    background: linear-gradient(to right, #e8e8e8 75%, #ffffff);
    overflow-x: hidden;
    padding: 16px 0px;
    border-radius: 16px;
    /* border: 1px solid red; */

    #s-title {
      display: flex;
      flex-direction: column;

      p {
        font-size: 2vw;
        font-weight: bold;
        color: var(--color-secondary-1);
      }
    }

    .carousel-container {
      position: relative;
      width: 90vw;
      height: 27.5vw;
      display: flex;
      align-items: center;
      overflow: hidden;
      border-radius: 10px;
      /* border: 1px solid red; */
    }
    .carousel-track {
      display: flex;
      align-self: center;
      margin-left: 27vw;
      gap: 10vw;
      transition: transform 0.5s ease-in-out;
    }

    .carousel-slide {
      /* border: 1px solid blue; */
      padding: 0;
      margin: 0;
      height: 20.75vw;
      min-width: 35vw;
      box-sizing: border-box;
      display: flex;
      justify-content: center;
      align-items: center;
      border-radius: 2vw;

      // iframe {
      //   display: block;
      //   width: 100%;
      //   height: 100%;
      //   aspect-ratio: 16 / 9;
      //   max-width: 35vw;
      //   border: none;
      //   border-radius: 2vw;
      // }
      video {
        display: block;
        width: 100%;
        height: 100%;
        aspect-ratio: 16 / 9;
        max-width: 35vw;
        border: none;
        border-radius: 2vw;
        object-fit: cover; // opcional para que rellene bien
      }
    }

    .carousel-button {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background-color: rgba(255, 193, 7, 0.9);
      border: none;
      color: white;
      font-size: 24px;
      font-weight: bold;
      // padding: 10px 15px;
      cursor: pointer;
      z-index: 10;
      border-radius: 50%;
      width: 48px;
      height: 48px;
      display: flex;
      align-items: center;
      justify-content: center;
      opacity: 0.7;
      transition:
        opacity 0.3s ease,
        background-color 0.3s ease;

      &:hover {
        opacity: 1;
        background-color: rgb(255, 193, 7);
      }

      &.prev {
        left: 1vw;
      }

      &.next {
        right: 1vw;
      }
    }

    .carousel-nav {
      position: absolute;
      bottom: 15px;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      gap: 10px;
    }
  }

  #personal {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    gap: 3vw;
    /* border: 1px solid red; */

    #s-title {
      display: flex;
      margin-top: 5vw;
      flex-direction: column;
      gap: 1vw;

      p {
        &:nth-child(1) {
          font-size: 2vw;
          font-weight: bold;
          color: var(--color-secondary-1);
        }

        &:nth-child(2) {
          font-weight: normal;
          font-size: 1.5vw;

          span {
            font-weight: bold;
            color: var(--color-primary-1);
          }
        }
      }
    }

    #pro-team {
      height: auto;
      width: 100%;

      #pro-card-container {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        gap: 1vw;
        width: 100%;

        .card {
          flex: 1;
          display: flex;
          align-items: center;
          flex-direction: column;
          gap: 0.2vw;
          position: relative;

          .img-pro {
            margin-bottom: 1vw;
            width: 13vw;
            height: 13vw;
            overflow: hidden;
            border-radius: 50%;

            img {
              width: 100%;
              height: 100%;
              object-fit: cover;
              object-position: center;
            }
          }

          .pro-name {
            font-weight: bold;
          }

          .pro-COP {
            font-weight: normal;
            font-size: 0.75vw;
          }

          .pro-area {
            color: grey;
            font-weight: normal;
            font-size: 0.75vw;
          }

          .pro-desc {
            max-width: 15vw;
            font-weight: normal;
            font-size: 0.75vw;
          }

          a {
            cursor: pointer;
            padding: 0.5vw 0 0 0;
            text-decoration: none;
            font-weight: bold;
          }
        }
      }
    }

    // #pro-container {
    //   display: grid;
    //   grid-template-columns: calc(80vw / 3) calc(80vw / 3) calc(80vw / 3);
    //   grid-template-rows: 28vw 28vw;
    //   column-gap: 1vw;
    //   /* border: 1px solid red; */
    //   padding: 0 2vw;

    //   #pro-card {
    //     border: 0.25vw solid white;
    //     display: flex;
    //     align-self: center;
    //     justify-self: center;
    //     width: 25vw;
    //     height: 25vw;
    //     /* background: rgb(103, 225, 255); */
    //     transition: all 0.4s;
    //     border-radius: 2vw;
    //     box-shadow: #604b4a30 0px 70px 30px -50px;
    //     font-size: 30px;
    //     font-weight: 900;
    //     /* z-index: -2; */
    //     overflow: hidden;
    //     position: relative;
    //     transition: all 0.4s;

    //     #pro-image {
    //       overflow: hidden;
    //       display: flex;
    //       align-self: center;
    //       justify-self: center;
    //       width: 25vw;
    //       height: 25vw;
    //       /* background: rgb(103, 225, 255); */
    //       transition: all 0.4s;
    //       border-radius: 2vw;
    //       box-shadow: #604b4a30 0px 70px 30px -50px;
    //       font-size: 30px;
    //       font-weight: 900;
    //     }

    //     #pro-desc {
    //       position: absolute;
    //       height: 8vw;
    //       width: 25vw;
    //       /* border: 1px solid red; */
    //       padding: 1vw;
    //       font-weight: normal;
    //       font-size: 1vw;
    //       bottom: 0;
    //       left: 0;
    //       overflow: hidden;
    //       background-color: var(--color-primary-1);
    //       transition: all 0.4s;

    //       #pro-name {
    //         position: absolute;
    //         font-weight: bold;
    //         top: 1vw;
    //         left: 1vw;
    //         color: white;
    //         font-size: 1.5vw;
    //         opacity: 1;
    //       }

    //       #pro-title {
    //         position: absolute;
    //         font-weight: normal;
    //         top: 3vw;
    //         left: 1vw;
    //         color: white;
    //         font-size: 1vw;
    //         opacity: 1;
    //       }

    //       #pro-full-text {
    //         opacity: 0;
    //         position: absolute;
    //         font-weight: normal;
    //         width: 22vw;
    //         text-align: justify;
    //         top: 4.5vw;
    //         left: 1vw;
    //         color: white;
    //         font-size: 0.75vw;
    //         transition: all 0.4s;
    //       }

    //       #pro-redes {
    //         position: absolute;
    //         bottom: 0.5vw;
    //         left: 1vw;
    //         display: flex;
    //         width: 22vw;
    //         flex-direction: row;
    //         gap: 1vw;
    //         align-content: center;
    //         align-items: center;
    //         justify-content: space-between;

    //         div {
    //           display: flex;
    //           flex-direction: row;
    //           gap: 1vw;

    //           a {
    //             display: flex;
    //             align-items: center;
    //             justify-content: center;
    //             width: 2vw;
    //             height: 2vw;
    //             overflow: hidden;
    //             background-color: var(--color-primary-2);
    //             border-radius: 50%;

    //             img {
    //               align-self: center;
    //               justify-self: center;
    //               width: 1vw;
    //               overflow: hidden;
    //               filter: invert(1);
    //               transition: all 250ms;
    //             }

    //             &:hover img {
    //               filter: invert(0);
    //             }
    //           }
    //         }

    //         #contact {
    //           text-decoration: none;
    //           color: white;
    //           font-weight: bold;
    //           padding: 0.5vw 1vw;
    //           border-radius: 999vw;
    //           background-color: var(--color-primary-2);
    //           transition: all 250ms;

    //           &:hover {
    //             color: black;
    //           }
    //         }
    //       }
    //     }

    //     &:hover {
    //       #pro-desc {
    //         height: 11vw;
    //         background-color: var(--color-primary-1);

    //         #pro-full-text {
    //           opacity: 1;
    //         }
    //       }
    //     }
    //   }
    // }
  }
}

@media screen and (max-width: 768px) {
  #body #services #tarj_price div div:nth-of-type(3) button {
    background-color: var(--color-secondary-1);
    margin-top: 1vw;
    width: 20vw;
    font-size: 2vw;
    border: none;
    border-radius: 0.5vw;
    color: white;
    padding: 1vw 3vw;
    text-transform: uppercase;
    transition: var(--color-secondary-2s) 1s ease;
  }
}
</style>
