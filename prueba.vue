<!-- :class="{ 'is-sticky-active': isStickyActive }" -->
<template>
  <nav ref="navElement">
    <div id="nav-main">
      <div id="logo-img" @click="routerMain()">
        <img src="/media/logos/logo_circle.png" alt="Dentodos" @click="routerMain()" />
      </div>

      <img src="/media/icons/menu_icon.svg" alt="Menú" class="toggle-btn" id="toggleBtn" />
      <div id="nav-options" class="nav-options">
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
</template>
<style>
// nav {
  //   top: 0;
  //   display: flex;
  //   align-items: start;
  //   border-radius: 10rem;
  //   color: white;
  //   font-weight: normal;
  //   margin: 0 auto;
  //   transition: all 400ms;
  //   #nav-main {
  //     background-color: #f8f8f8;
  //     display: flex;
  //     width: 100%;
  //     position: relative;
  //     align-items: center;
  //     justify-content: space-between;
  //     box-sizing: border-box;
  //     padding: 4vw 5vw;
  //     color: black;
  //     font-weight: bold;
  //     z-index: 100;

  //     .is-sticky {
  //       box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  //       background-color: var(--color-primary-2);
  //       height: 4vw;
  //       padding: 0.5vw 1vw;
  //     }

  //     #logo-img {
  //       cursor: pointer;

  //       img {
  //         width: 4.5vw;
  //       }
  //     }

  //     #toggleBtn {
  //       height: 1.6rem;
  //       background: none;
  //       border: none;
  //       cursor: pointer;
  //       object-fit: contain;
  //     }

  //     #nav-options {
  //       display: none;
  //       width: 100%;
  //       position: absolute;
  //       max-height: 0px;
  //       transition: all 300ms;
  //       top: 100%;
  //       left: 0;
  //       background-color: #f8f8f8;
  //       flex-direction: column;
  //       gap: 1.5rem;
  //       padding: 0 4vw;

  //       div {
  //         a {
  //           padding: 1.5vw 0;
  //           font-size: 1vw;
  //           color: black;
  //           text-decoration: none;
  //           transition: all 250ms;
  //           cursor: pointer;
  //           font-size: $font-size-md;

  //           &:hover {
  //             color: var(--color-primary-1);
  //             text-decoration-line: underline;
  //             text-decoration-color: var(--color-primary-1);
  //             text-decoration-thickness: 0.25vw;
  //             text-underline-offset: 0.5vw;
  //           }
  //         }

  //         .dropdown {
  //           position: relative;
  //           cursor: pointer;

  //           .dropdown-toggle {
  //             display: flex;
  //             align-items: center;

  //             .arrow-down {
  //               transition: transform 0.3s ease;
  //             }

  //             .arrow-rotated {
  //               transform: rotate(180deg);
  //             }
  //           }

  //           .dropdown-submenu {
  //             display: none !important;
  //             position: absolute;
  //             background-color: white;
  //             min-width: 160px;
  //             box-shadow: 0px 8px 16px rgba(0, 0, 0, 0.2);
  //             display: flex;
  //             flex-direction: column;
  //             top: 75%;

  //             a {
  //               padding: 8px 12px;
  //               text-decoration: none;
  //               display: block;
  //             }
  //           }

  //           .is-open {
  //             display: block !important;
  //           }
  //         }
  //       }

  //       .options__cotiza {
  //         text-decoration: none;
  //         color: white;
  //         background-color: var(--color-primary-1);
  //         padding: 0.75vw 2vw;
  //         border-radius: 9999px;
  //         font-size: $font-size-md;
  //       }
  //     }

  //     #nav-options.show {
  //       display: flex;
  //       max-height: 100vh;
  //       padding: 2vw 4vw;
  //     }
  //   }
  // }
</style>
<template>
  <nav class="navbar">
    <div class="navbar-brand">MiSitio</div>
    <div class="navbar-toggle" @click="toggleMenu">☰</div>

    <div :class="['navbar-menu', { show: showMenu }]" id="menu">
      <div v-for="(linkItem, index) in mainNavLinks" :key="index" class="nav-item">
        <!-- Enlace simple -->
        <a class="linkItem" @click="goTo(linkItem.href)" v-if="!linkItem.submenu">
          {{ linkItem.label }}
        </a>

        <!-- Enlace con submenú -->
        <div v-else :class="['dropdown', { open: openStates[index] }]">
          <a class="linkItem" @click.prevent="openDropdownMenu(index)">
            {{ linkItem.label }}
            <img class="arrow-down" src="/media/icons/arrow_drop_down.svg" />
          </a>
          <div class="dropdown-menu" v-for="subItem in linkItem.submenu" :key="subItem.label">
            <a @click="goTo(subItem.href)">{{ subItem.label }}</a>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>
