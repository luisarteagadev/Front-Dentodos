<template>
  <q-page>
    <NavigationBar :mainNavLinks="navigationMenuItems" />
    <div id="VSL">
      <p>El poder de una sonrisa: Conoce su historia</p>
    </div>
    <div id="Header">
      <div id="prob-ident">
        <p>¿Te sientes inseguro al sonreír?</p>
        <div>
          <div>
            <p>¿Evitas las fotos o reuniones por miedo a mostrar tu sonrisa?</p>
            <p>
              ¿Sientes que tu sonrisa impacta tu confianza y oportunidades personales o
              profesionales?
            </p>
          </div>
        </div>
      </div>
      <div class="image">
        <img src="/public/media/photos/med-campain.jpg" alt="" />
      </div>
    </div>
    <!-- <div id="Header">
      <div class="text">
        <p>¡Transforma tu Sonrisa y Transforma tu Vida!</p>
        <p>
          Con nuestro exclusivo Diseño de Sonrisa, tu imagen se convertirá en tu mejor carta de
          presentación.
        </p>
      </div>
      <div class="image">
        <img src="/public/media/photos/med-campain.jpg" alt="" />
      </div>
    </div> -->

    <!-- <div id="VSL">
      <p>El poder de una sonrisa: Conoce su historia</p>
      <div>
        <video autoplay loop muted playsinline>
          <source src="/media/videos/4489831-hd_1280_720_50fps.mp4" />
          Tu navegador no soporta la reproducción de video.
        </video>
      </div>
    </div>

    <div id="Tratamiento">
      <p>¿Qué es el Diseño de Sonrisa?</p>
      <p>
        "Es un tratamiento integral que combina tecnología de vanguardia y la experiencia de
        nuestros especialistas para lograr una sonrisa natural, armoniosa y en equilibrio con tu
        rostro. Usamos un enfoque personalizado para transformar tu sonrisa y que refleje lo mejor
        de ti."
      </p>
    </div>

    <div id="prob-ident">
      <p>¿Te sientes inseguro al sonreír?</p>
      <div>
        <div>
          <p>¿Evitas las fotos o reuniones por miedo a mostrar tu sonrisa?</p>
          <p>
            ¿Sientes que tu sonrisa impacta tu confianza y oportunidades personales o profesionales?
          </p>
        </div>
        <p>
          Una sonrisa alineada y natural puede devolverte la seguridad para hablar, sonreír y
          disfrutar sin incomodidades. Ya no tendrás que evitar fotos ni reuniones: recuperarás la
          confianza en ti y proyectarás una imagen más segura, tanto en lo personal como en lo
          profesional
        </p>
      </div>
    </div>

    <div id="sol-iden">
      <p>¿Por qué elegirnos para tu Diseño de Sonrisa?</p>
      <div>
        <div>
          <ul>
            <li>
              <span>Recupera tu Confianza:</span> Una sonrisa alineada y estética te hará sentir
              seguro en cada ocasión, desde una foto hasta una reunión importante.
            </li>
            <li>
              <span>Resultados naturales y personalizados:</span> Utilizamos diseño digital para
              crear una sonrisa que se adapta a tus rasgos faciales y estilo personal.
            </li>
            <li>
              <span>Tecnología de vanguardia</span> Trabajamos con programas digitales de última
              generación que garantizan precisión y seguridad.
            </li>
            <li>
              <span>Atención centrada en ti</span>Te evaluamos de forma personalizada, con
              fotografías y diseñamos una planificación según tus necesidades.
            </li>
            <li>
              <span>Cambios visibles desde la segunda sesión</span>
              En solo 3 sesiones puedes ver la transformación total de tu sonrisa.
            </li>
            <li>
              <span>Resultados comprobados y con garantía</span>
              Más de 200 pacientes ya confiaron en nosotros y hoy disfrutan de una sonrisa renovada.
            </li>
            <li>
              <span> Precios accesibles</span>
              Manejamos los costos más competitivos del mercado, sin comprometer la calidad de tu
              tratamiento.
            </li>
          </ul>
        </div>
        <div>
          <ul>
            <li>Consulta inicial y diagnóstico digital.</li>
            <li>Diseño personalizado y simulación de resultados.</li>
            <li>Procedimiento realizado por especialistas experimentados.</li>
          </ul>
        </div>
      </div>
    </div> -->

    <MapAndForm />
    <EndFooter />
  </q-page>
</template>

<script>
import NavigationBar from 'src/components/Navigation/NavegationBar.vue'
import MapAndForm from 'src/components/MapForm.vue'
import EndFooter from 'src/components/EndFooter.vue'
import { ref } from 'vue'

export default {
  components: { NavigationBar, MapAndForm, EndFooter },
  setup() {
    return {
      slide: ref(1),
      autoplay: ref(true),
      pro_view: ref(false),
      navigationMenuItems: ref([
        { label: 'Home', href: '/' }, // Puedes usar Vue Router paths aquí
        { label: 'Video Descriptivo', href: 'VSL' },
        { label: 'Tratamiento', href: 'Tratamiento' },
        {
          label: 'Reseñas Google',
          href: 'reviews',
        },
        // Nota: El target="_blank" necesitaría manejarse dentro del componente NavigationBar si quieres que algunos enlaces se abran en nueva pestaña
      ]),
    }
  },
}
</script>

<style lang="scss" scoped>
@import 'src/css/diseniosonrisa.scss';
</style>
