<template>
  <q-page>
    <NavigationBar :mainNavLinks="navigationMenuItems" />

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

    <div id="VSL">
      <p>El poder de una sonrisa: Conoce su historia</p>
      <div>
        <video autoplay loop muted playsinline>
          <source src="/public/media/videos/4489831-hd_1280_720_50fps.mp4" />
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
    </div>

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
#Header {
  // border: 1px solid red;
  margin: 0 5vw;
  overflow: hidden;
  display: flex;
  flex-direction: row;
  gap: 5vw;
  align-content: center;
  justify-content: space-between;
  padding: 1vw;

  div {
    flex: 1;
  }

  .text {
    background-color: var(--color-primary-1-medium);
    border-radius: 3vw;
    display: flex;
    flex-direction: column;
    align-content: start;
    justify-content: center;
    padding: 3vw;

    p {
      color: white;

      &:nth-child(1) {
        font-weight: bold;
        font-size: 2.5vw;
        margin-bottom: 2vw;
      }

      &:nth-child(2) {
        font-weight: normal;
        font-size: 1.25vw;
      }
    }
  }

  .image {
    padding: 0;
    margin: 0;
    display: flex;
    align-content: center;
    justify-content: center;
    img {
      border-radius: 2vw;
      width: 30vw;
      object-fit: cover;
      object-position: center;
    }
  }
}

#VSL {
  margin: 2vw 6vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2vw;
  overflow: hidden;

  p {
    font-weight: bold;
    font-size: 3vw;
    color: var(--color-primary-2);
  }

  div {
    aspect-ratio: 16/9;
    width: 50vw;
    overflow: hidden;
    border-radius: 2vw;

    video {
      overflow: hidden;
      width: 100%;
    }
  }
}

#Tratamiento {
  margin: 4vw 6vw 3vw 6vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2vw;
  overflow: hidden;

  p {
    &:nth-child(1) {
      font-weight: bold;
      font-size: 2.3vw;
      color: var(--color-primary-2);
    }

    &:nth-child(2) {
      font-weight: 500;
      text-align: center;
      font-size: 1.7vw;
      color: var(--color-primary-1);
    }
  }
}

#prob-ident {
  margin: 4vw 6vw 3vw 6vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2vw;
  overflow: hidden;

  p {
    font-weight: bold;
    font-size: 2.3vw;
    color: var(--color-primary-2);
  }

  div {
    display: flex;
    flex-direction: row;
    align-content: center;
    justify-content: space-between;
    gap: 5vw;
    padding: 0 5vw;
    width: 100%;

    div {
      all: unset;
      display: flex;
      flex-direction: column;
      align-content: center;
      padding: 2vw;
      width: 60vw;
      gap: 1vw;

      p {
        all: unset;
        width: 100%;
        &:nth-child(1) {
          font-weight: bold;
          font-size: 2vw;
          justify-self: start;
          color: var(--color-primary-1);
          margin-bottom: 2vw;
        }

        &:nth-child(2) {
          font-weight: 500;
          text-align: center;
          font-size: 1.5vw;
          color: var(--color-secondary-1);
        }
      }
    }

    p {
      display: flex;
      background-color: var(--color-primary-1-medium);
      justify-self: center;
      align-items: center;
      align-self: center;
      font-weight: normal;
      font-size: 1.1vw;
      height: 20vw;
      width: 25vw;
      padding: 2vw;
      border-radius: 2vw;
      color: white;
    }
  }
}

// Asume que tienes variables de color globales definidas, por ejemplo:
// :root {
//   --color-primary-1: #2ca9db; /* Azul principal */
//   --color-secondary-1: #355c81; /* Azul más oscuro */
//   --color-secondary-2: #192b44; /* Azul muy oscuro (para texto) */
//   --color-text-light: #f8f9fa;  /* Un blanco hueso o gris muy claro */
//   --color-text-muted: #6c757d; /* Un gris para texto secundario */
//   --color-background-light: #ffffff;
//   --color-border-light: #e9ecef;
// }

#sol-iden {
  margin: 0 6vw;
  padding: 3rem 1.5rem; // Espaciado generoso
  background-color: var(--color-background-light, #fff); // Fondo limpio
  // border-top: 5px solid var(--color-primary-1); // Un toque de color arriba
  // border-bottom: 5px solid var(--color-primary-1); // Y abajo
  margin-bottom: 3rem; // Espacio después de la sección

  // Título principal de la sección
  > p {
    text-align: center;
    font-size: clamp(1.8rem, 4vw, 2.8rem); // Tamaño de fuente responsive
    font-weight: bold;
    color: var(--color-secondary-1, #355c81);
    margin-bottom: 2.5rem;
    line-height: 1.3;
  }

  // Contenedor de las dos listas/columnas
  > div {
    display: flex;
    flex-wrap: wrap; // Para que se apilen en pantallas pequeñas
    gap: 2.5rem; // Espacio entre las columnas de listas
    justify-content: center; // Centrar las columnas si no ocupan todo el ancho

    // Cada columna (div que contiene un ul)
    > div {
      flex: 1 1 320px; // Permite que crezcan, se encojan, con una base de 320px
      background-color: var(--color-text-light, #f8f9fa); // Un fondo sutil para destacar las listas
      padding: 2rem;
      border-radius: 8px; // Bordes redondeados suaves
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05); // Sombra muy sutil

      ul {
        list-style-type: none; // Quitar viñetas por defecto
        padding-left: 0;
        margin: 0;

        li {
          display: flex; // Para alinear el "ícono" con el texto
          flex-direction: column;
          align-items: flex-start; // Alinear al inicio si el texto es multilínea
          padding: 0.8rem 0; // Espaciado vertical para cada ítem
          color: var(--color-secondary-2, #192b44);
          font-size: clamp(1.4rem, 1.5vw, 1rem);
          line-height: 1.6;

          &:not(:last-child) {
            border-bottom: 1px solid var(--color-border-light, #e9ecef); // Separador sutil
          }

          // Ícono personalizado usando un pseudo-elemento ::before
          // &::before {
          //   content: '✓'; // Puedes cambiarlo por '•', '➤', u otro símbolo Unicode
          //   // Si tuvieras acceso a Quasar aquí, podrías usar <q-icon>
          //   color: var(--color-primary-1, #2ca9db); // Color del ícono
          //   font-weight: bold;
          //   font-size: 1.2em; // Un poco más grande que el texto
          //   margin-right: 0.8rem; // Espacio entre el ícono y el texto
          //   line-height: 1.4; // Para alinear mejor con la primera línea de texto
          //   flex-shrink: 0; // Para que el ícono no se encoja
          // }

          // Estilo para los <span> dentro de los <li> (ej. "Recupera tu Confianza:")
          span {
            font-weight: 600; // Semibold
            color: var(--color-secondary-1, #355c81); // Un color distintivo
            margin-right: 0.3em; // Pequeño espacio después del span
            // display: block; // Si quieres que el span esté en su propia línea
            // margin-bottom: 0.2rem;
            &::before {
              content: '✓'; // Puedes cambiarlo por '•', '➤', u otro símbolo Unicode
              // Si tuvieras acceso a Quasar aquí, podrías usar <q-icon>
              color: var(--color-primary-1, #2ca9db); // Color del ícono
              font-weight: bold;
              font-size: 1.2em; // Un poco más grande que el texto
              margin-right: 0.8rem; // Espacio entre el ícono y el texto
              line-height: 1.4; // Para alinear mejor con la primera línea de texto
              flex-shrink: 0; // Para que el ícono no se encoja
            }
          }
        }
      }
    }
    > div:nth-child(2) {
      ul {
        li {
          flex-direction: row;
          &::before {
            content: '✓'; // Puedes cambiarlo por '•', '➤', u otro símbolo Unicode
            // Si tuvieras acceso a Quasar aquí, podrías usar <q-icon>
            color: var(--color-primary-1, #2ca9db); // Color del ícono
            font-weight: bold;
            font-size: 1.2em; // Un poco más grande que el texto
            margin-right: 0.8rem; // Espacio entre el ícono y el texto
            line-height: 1.4; // Para alinear mejor con la primera línea de texto
            flex-shrink: 0; // Para que el ícono no se encoja
          }
        }
      }
    }
  }
}

// Ajustes para pantallas más pequeñas
@media (max-width: 768px) {
  #sol-iden {
    padding: 2rem 1rem;

    > p {
      // Título principal
      font-size: clamp(1.6rem, 5vw, 2.2rem);
      margin-bottom: 2rem;
    }

    > div {
      // Contenedor de las columnas
      gap: 2rem; // Reducir el espacio entre columnas apiladas

      > div {
        // Cada columna
        padding: 1.5rem;
        flex-basis: 100%; // Para que ocupen todo el ancho y se apilen
      }
    }
  }
}

@media (max-width: 480px) {
  #sol-iden {
    #sident-list-cols > div > ul > li {
      font-size: clamp(0.85rem, 3vw, 0.95rem); // Texto un poco más pequeño en móviles muy pequeños
      &::before {
        font-size: 1.1em;
        margin-right: 0.6rem;
      }
    }
  }
}
</style>
