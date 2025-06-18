<template>
  <div id="reviews">
    <div id="s-title">
      <p></p>
      <p>Reseñas de google</p>
      <p></p>
    </div>
    <div id="r-c-container">
      <div class="card" v-for="(r, index) in reviews" :key="index">
        <div class="card-profile-section">
          <div class="avatar">{{ r.iniciales }}</div>
          <div class="user-info">
            <div class="user-name">{{ r.nombre }}</div>
          </div>
        </div>

        <div class="rating-stars">
          {{ '★'.repeat(r.estrellas) + '☆'.repeat(5 - r.estrellas) }}
        </div>

        <p class="review-text">
          {{
            expanded[index]
              ? r.comentario
              : r.comentario.slice(0, 250) + (r.comentario.length > 250 ? '...' : '')
          }}
        </p>

        <div class="read-more-link" v-if="r.comentario.length > 250" @click="toggleReadMore(index)">
          {{ expanded[index] ? 'Leer menos' : 'Leer más' }}
        </div>
      </div>
    </div>
  </div>

  <div id="map-and-form">
    <div id="bg"></div>
    <div id="forms">
      <div id="container-form-map">
        <div id="s-title">
          <p>Separa tu cita o solicita tu cotización</p>
        </div>

        <div id="separate-appointment">
          <form class="form">
            <p class="title">Registrar una cita</p>
            <p class="message">Anímate a mejorar tu salud bucal</p>

            <label>
              <input required="" placeholder="Nombres" type="text" class="input" />
              <!-- <span>Nombres</span> -->
            </label>

            <label>
              <input required="" placeholder="Apellido" type="text" class="input" />
              <!-- <span>Apellido</span> -->
            </label>
            <label>
              <input required="" placeholder="Email" type="email" class="input" />
              <!-- <span>Email</span> -->
            </label>
            <label>
              <input required="" placeholder="Telefono" type="text" class="input" />
              <!-- <span>Email</span> -->
            </label>

            <label>
              <input required="" placeholder="Servicio" type="text" class="input" />
              <!-- <span>Servicio</span> -->
            </label>
            <label>
              <input required="" placeholder="Mensaje (Opcional)" type="text" class="input" />
              <!-- <span>Mensaje (Opcional)</span> -->
            </label>
            <button class="submit">Solicitar</button>
            <p class="signin">Buscas conocer nuestros servicios? <a href="#">Ver Servicios</a></p>
          </form>

          <div id="map">
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2758.8627505224426!2d-77.05854473807422!3d-12.087412178864072!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x9105c9c0e36cf265%3A0x68f04984c5067ea4!2sConsultorio%20Odontol%C3%B3gico%20Dentodos!5e0!3m2!1ses!2spe!4v1747638896576!5m2!1ses!2spe"
              width="800"
              height="450"
              style="border: 0"
              allowfullscreen=""
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
            ></iframe>
            <button class="waze-button" @click="redirectToWaze">
              <span> Ir con Waze </span>
              <img class="waze-icon" src="/media/icons/waze.png" alt="waze" />
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- <div id="reviews">
      <p id="r-title">Nuestras reseñas</p>
      <div id="r-c-container">
        <div class="card">
          <div class="card-profile-section">
            <div class="avatar">DJ</div>
            <div class="user-info">
              <div class="user-name">Donald Jackman</div>
              <div class="user-title">Content Creator</div>
            </div>
          </div>

          <div class="rating-stars">★★★★★</div>

          <p class="review-text">
            I've been using Imagify for nearly two years, primarily for Instagram, and it has been
            incredibly user-friendly, making my work much easier.
          </p>

          <div class="read-more-link">Read more</div>
        </div>
        <div class="card">
          <div class="card-profile-section">
            <div class="avatar">DJ</div>
            <div class="user-info">
              <div class="user-name">Donald Jackman</div>
              <div class="user-title">Content Creator</div>
            </div>
          </div>

          <div class="rating-stars">★★★★★</div>

          <p class="review-text">
            I've been using Imagify for nearly two years, primarily for Instagram, and it has been
            incredibly user-friendly, making my work much easier.
          </p>

          <div class="read-more-link">Read more</div>
        </div>
        <div class="card">
          <div class="card-profile-section">
            <div class="avatar">DJ</div>
            <div class="user-info">
              <div class="user-name">Donald Jackman</div>
              <div class="user-title">Content Creator</div>
            </div>
          </div>

          <div class="rating-stars">★★★★★</div>

          <p class="review-text">
            I've been using Imagify for nearly two years, primarily for Instagram, and it has been
            incredibly user-friendly, making my work much easier.
          </p>

          <div class="read-more-link">Read more</div>
        </div>
      </div>
    </div> -->

    <div id="c_wsp">
      <a href="https://api.whatsapp.com/send?phone=51932033644" target="_blank">
        <img src="/media/icons/whatsapp.png" alt="" />
      </a>
    </div>
  </div>
</template>

<script>
import { REVIEWS } from '../constants'

export default {
  data() {
    return {
      reviews: REVIEWS,
      expanded: [],
    }
  },
  created() {
    this.expanded = this.reviews.map(() => false)
  },
  methods: {
    toggleReadMore(index) {
      this.expanded[index] = !this.expanded[index]
    },
    redirectToWaze() {
      // Cambia por la ubicación deseada
      const latitude = -12.087036599196333
      const longitude = -77.05754813492838

      const wazeUrl = `https://waze.com/ul?ll=${latitude},${longitude}&navigate=yes`
      window.open(wazeUrl, '_blank')
    },
  },
}
</script>

<style lang="scss" scoped>
@import '../css/mapform.scss';
</style>
