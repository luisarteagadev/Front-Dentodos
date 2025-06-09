<template>
  <div id="map-and-form">
    <div id="bg"></div>

    <div id="forms">
      <div id="s-title">
        <p>Separa tu cita o solicita tu cotización</p>
      </div>

      <div id="f-content">
        <form class="form">
          <p class="title">Registrar una cita</p>
          <p class="message">Anímate a mejorar tu salud bucal</p>
          <div class="flex">
            <label>
              <input required="" placeholder="" type="text" class="input" />
              <span>Nombres</span>
            </label>

            <label>
              <input required="" placeholder="" type="text" class="input" />
              <span>Apellido</span>
            </label>
          </div>

          <label>
            <input required="" placeholder="" type="email" class="input" />
            <span>Email</span>
          </label>

          <label>
            <input required="" placeholder="" type="text" class="input" />
            <span>Servicio</span>
          </label>
          <label>
            <input required="" placeholder="" type="text" class="input" />
            <span>Mensaje (Opcional)</span>
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

    <div id="reviews">
      <p id="r-title">Nuestras reseñas</p>
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

          <div
            class="read-more-link"
            v-if="r.comentario.length > 250"
            @click="toggleReadMore(index)"
          >
            {{ expanded[index] ? 'Leer menos' : 'Leer más' }}
          </div>
        </div>
      </div>
    </div>

    <div id="c_wsp">
      <a href="https://api.whatsapp.com/send?phone=51999988877" target="_blank">
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
  },
}
</script>

<style lang="scss" scoped>
p {
  margin: 0;
  padding: 0;
}
#map-and-form {
  #bg {
    background-color: transparent; /* Light blue background color */
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1440 320'%3E%3Cpath fill='%232CA9DB' fill-opacity='0.5' d='M0,160L48,181.3C96,203,192,245,288,261.3C384,277,480,267,576,234.7C672,203,768,149,864,138.7C960,128,1056,160,1152,186.7C1248,213,1344,235,1392,245.3L1440,256L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z'%3E%3C/path%3E%3Cpath fill='%232CA9DB' fill-opacity='0.3' d='M0,192L48,197.3C96,203,192,213,288,229.3C384,245,480,267,576,277.3C672,288,768,288,864,261.3C960,235,1056,181,1152,165.3C1248,149,1344,171,1392,181.3L1440,192L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z'%3E%3C/path%3E%3Cpath fill='%232CA9DB' fill-opacity='0.2' d='M0,224L48,213.3C96,203,192,181,288,181.3C384,181,480,203,576,224C672,245,768,267,864,261.3C960,256,1056,224,1152,213.3C1248,203,1344,213,1392,218.7L1440,224L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z'%3E%3C/path%3E%3C/svg%3E");
    background-size: cover;
    background-position: center bottom;
    background-repeat: no-repeat;
    width: 100%;
    padding: 0 0;
    position: relative;
    overflow: hidden;
    height: 200px;
    margin-bottom: 0px;
    padding-bottom: 0px;
    z-index: 1;
  }

  #forms {
    background-color: rgb(44, 169, 219, 0.725);
    display: flex;
    width: 100%;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;

    margin: 0;
    padding: 0;
    color: white;
    /* border: 1px solid red; */

    #s-title {
      display: flex;
      margin-top: 5vw;
      flex-direction: column;
      gap: 1vw;
      color: white;

      p {
        &:nth-child(1) {
          color: white;
          font-size: 2vw;
          font-weight: bold;
          color: white;
        }
      }
    }

    #f-content {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin: 0 2vw;
      width: 86vw;
      /* border: 1px solid white; */
      padding: 5vw 2vw;

      .form {
        display: flex;
        flex-direction: column;
        gap: 1vw;
        width: 30vw;
        background-color: #fff;
        padding: 2vw;
        border-radius: 2vw;
        position: relative;

        label {
          position: relative;
          display: flex;
          flex-direction: column;
          align-items: start;

          .input {
            width: 100%;
            padding: 1vw 1vw 1.5vw 1vw;
            outline: 0;
            border: 1px solid rgba(105, 105, 105, 0.397);
            border-radius: 1vw;
          }

          .input + span {
            position: absolute;
            left: 1vw;
            top: 2vw;
            color: grey;
            font-size: 0.9em;
            cursor: text;
            transition: 0.3s ease;
          }

          .input:placeholder-shown + span {
            top: 15px;
            font-size: 0.9em;
          }

          .input:focus + span,
          .form label .input:valid + span {
            top: 2.25vw;
            font-size: 0.7em;
            font-weight: 600;
          }

          .input:valid + span {
            color: green;
          }

          .input:invalid:not(:placeholder-shown) + span {
            color: red;
          }
        }
      }

      .title {
        font-size: 2vw;
        color: var(--color-primary-2);
        font-weight: bold;
        letter-spacing: -1px;
        position: relative;
        display: flex;
        align-items: center;
        padding-left: 3vw;

        @keyframes pulse {
          from {
            transform: scale(0.9);
            opacity: 1;
          }

          to {
            transform: scale(1.8);
            opacity: 0;
          }
        }

        &::before,
        .title::after {
          position: absolute;
          content: '';
          height: 1vw;
          width: 1vw;
          border-radius: 50%;
          left: 0px;
          background-color: var(--color-primary-2);
        }

        &::before {
          width: 1.8vw;
          height: 1.8vw;
          background-color: var(--color-primary-2);
        }

        &::after {
          width: 1.8vw;
          height: 1.8vw;
          animation: pulse 1s linear infinite;
        }
      }

      .message,
      .signin {
        color: rgba(88, 87, 87, 0.822);
        font-size: 1vw;
      }

      .signin {
        text-align: center;

        a {
          color: var(--color-primary-2);

          &:hover {
            text-decoration: underline var(--color-primary-2);
          }
        }
      }

      .flex {
        display: flex;
        flex-direction: row;
        width: 100%;
        gap: 0.6vw;

        label {
          &:nth-child(1) {
            width: 12.6vw;
          }

          &:nth-child(2) {
            width: 12.6vw;
          }
        }
      }

      .submit {
        border: none;
        outline: none;
        background-color: var(--color-primary-2);
        padding: 1vw;
        border-radius: 1vw;
        color: #fff;
        font-size: 1vw;
        transform: 0.3s ease;

        &:hover {
          background-color: rgb(56, 90, 194);
        }
      }

      #map {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 50vw;
        height: 33vw;
        border-radius: 2vw;
        overflow: hidden;

        iframe {
          width: 100%;
          height: 100%;
          border: none;
          border-radius: 2vw;
        }
      }
    }
  }

  #c_wsp {
    all: unset;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 4vw;
    height: 4vw;
    position: fixed;
    background-color: #25d366;
    bottom: 2vw;
    right: 2vw;
    z-index: 1000;
    border-radius: 50%;

    a {
      color: white;
      text-decoration: none;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    img {
      display: flex;
      align-self: center;
      justify-self: center;
      width: 2vw;
      filter: invert(1);
      transition: all 250ms;

      &:hover {
        filter: invert(0);
      }
    }
  }

  // #reviews {
  //   width: 100%;
  //   background-color: rgb(44, 169, 219, 0.725);
  //   padding-bottom: 5vw;
  //   margin-bottom: -1vw;
  //   display: flex;
  //   flex-direction: column;
  //   align-items: center;
  //   gap: 2vw;

  //   #r-title {
  //     text-align: center;
  //     font-weight: bold;
  //     color: white;
  //     font-size: 2.5vw;
  //   }

  //   #r-c-container {
  //     display: flex;
  //     flex-direction: row;
  //     gap: 1.5vw;
  //   }

  //   .card {
  //     max-width: 24vw;
  //     border-width: 0.1vw;
  //     border-style: solid;
  //     border-color: #d1d5db;
  //     border-radius: 0.5vw;
  //     box-shadow:
  //       0 10px 15px -3px rgba(0, 0, 0, 0.1),
  //       0 4px 6px -2px rgba(0, 0, 0, 0.05);
  //     background-color: #ffffff;
  //     padding: 1.5vw;
  //   }

  //   .card > * + * {
  //     margin-top: 1vw;
  //   }

  //   .card-profile-section {
  //     display: flex;
  //     align-items: center;
  //   }

  //   .card-profile-section > * + * {
  //     margin-left: 1vw;
  //   }

  //   .avatar {
  //     height: 3vw;
  //     width: 3vw;
  //     display: flex;
  //     align-items: center;
  //     justify-content: center;
  //     background-color: #ef4444;
  //     color: #ffffff;
  //     font-size: 1.125vw;
  //     font-weight: bold;
  //     border-radius: 9999px;
  //   }

  //   .user-name {
  //     color: #111827;
  //     font-weight: 500;
  //   }

  //   .user-title {
  //     color: #4b5563;
  //     font-size: 0.875vw;
  //   }

  //   .rating-stars {
  //     display: flex;
  //     color: #ef4444;
  //     font-size: 1.25vw;
  //   }

  //   .review-text {
  //     color: #374151;
  //     line-height: 1.625;
  //     font-size: 1vw;
  //   }

  //   .read-more-link {
  //     color: #ef4444;
  //     font-weight: 500;
  //     cursor: pointer;
  //   }

  //   .read-more-link:hover {
  //     text-decoration: underline;
  //   }
  // }
  #reviews {
    width: 100%;
    background-color: rgba(44, 169, 219, 0.725);
    padding-bottom: 5vw;
    margin-bottom: -1vw;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2vw;
    padding-right: 16px;
    padding-left: 16px;
    #r-title {
      text-align: center;
      font-weight: bold;
      color: white;
      font-size: 2.5vw;
    }

    #r-c-container {
      display: flex;
      flex-direction: row;
      gap: 1.5vw;
      overflow-x: auto;
      scroll-snap-type: x mandatory;
      padding: 1vw 2vw;
      -webkit-overflow-scrolling: touch;

      &::-webkit-scrollbar {
        height: 0.6vw;
      }

      &::-webkit-scrollbar-thumb {
        background: #ccc;
        border-radius: 10px;
      }

      &::-webkit-scrollbar-track {
        background: transparent;
      }
    }

    .card {
      flex: 0 0 calc((100% - 6vw) / 4); // 4 tarjetas con espacio de 1.5vw entre cada una
      scroll-snap-align: start;
      border: 1px solid #d1d5db;
      border-radius: 0.5vw;
      box-shadow:
        0 10px 15px -3px rgba(0, 0, 0, 0.1),
        0 4px 6px -2px rgba(0, 0, 0, 0.05);
      background-color: #ffffff;
      padding: 1.5vw;
      display: flex;
      flex-direction: column;
      min-width: 220px;
      max-width: 500px;
    }

    .card > * + * {
      margin-top: 1vw;
    }

    .card-profile-section {
      display: flex;
      align-items: center;

      > * + * {
        margin-left: 1vw;
      }
    }

    .avatar {
      height: 3vw;
      width: 3vw;
      min-height: 40px;
      min-width: 40px;
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: #ef4444;
      color: #ffffff;
      font-size: 1.125vw;
      font-weight: bold;
      border-radius: 50%;
    }

    .user-name {
      color: #111827;
      font-weight: 500;
      font-size: 1vw;
    }

    .user-title {
      color: #4b5563;
      font-size: 0.875vw;
    }

    .rating-stars {
      color: #ef4444;
      font-size: 1.25vw;
    }

    .review-text {
      color: #374151;
      line-height: 1.625;
      font-size: 1vw;
    }

    .read-more-link {
      color: #ef4444;
      font-weight: 500;
      cursor: pointer;

      &:hover {
        text-decoration: underline;
      }
    }
  }
}
</style>
