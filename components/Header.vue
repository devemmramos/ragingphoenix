<template>
  <header>
    <div class="particles-js">
       <Particles
        id="tsparticles"
          :options="{
	fpsLimit: 60,
	particles: {
		number: {
			value: 80,
			density: {
				enable: true,
				value_area: 800
			}
		},
		color: {
			value: '#ffffff'
		},
		shape: {
			type: 'circle',
			stroke: {
				width: 0,
				color: '#000000'
			},
			polygon: {
				nb_sides: 5
			},
			image: {
				src: 'img/github.svg',
				width: 100,
				height: 100
			}
		},
		opacity: {
			value: 0.5,
			random: false,
			anim: {
				enable: false,
				speed: 1,
				opacity_min: 0.1,
				sync: false
			}
		},
		size: {
			value: 3,
			random: true,
			anim: {
				enable: false,
				speed: 20,
				size_min: 0.1,
				sync: false
			}
		},
		line_linked: {
			enable: true,
			distance: 150,
			color: '#ffffff',
			opacity: 0.4,
			width: 1
		},
		move: {
			enable: true,
			speed: 3,
			direction: 'none',
			random: false,
			straight: false,
			out_mode: 'out',
			bounce: false,
			attract: {
				enable: false,
				rotateX: 600,
				rotateY: 1200
			}
		}
	},
	interactivity: {
		detect_on: 'canvas',
		events: {
			onhover: {
				enable: true,
				mode: 'grab'
			},
			onclick: {
				enable: true,
				mode: 'push'
			},
			resize: true
		},
		modes: {
			grab: {
				distance: 140,
				line_linked: {
					opacity: 1
				}
			},
			bubble: {
				distance: 400,
				size: 40,
				duration: 2,
				opacity: 8,
				speed: 3
			},
			repulse: {
				distance: 200,
				duration: 0.4
			},
			push: {
				particles_nb: 4
			},
			remove: {
				particles_nb: 2
			}
		}
	},
	retina_detect: true
}"
        />
    </div>
    <nav
      class="social-header relative flex flex-wrap items-center justify-between z-10"
    >
      <div
        class="
          container
          mx-auto
          flex flex-wrap
          items-center
          justify-center
          md:justify-between
        "
      >
        <div
          class="
            hidden
            w-full
            relative
            flex
            justify-between
            lg:w-auto
            lg:static
            lg:block
            lg:justify-start
          "
        >
          <a
            class="
              text-white-50
              leading-relaxed
              inline-block
              mr-4
              py-2
              whitespace-nowrap
              uppercase
              text-white
            "
            href="#pablo"
          >
            The official home of RagingPhoenix
          </a>
        </div>
        <div class="lg:flex lg:flex-grow items-center">
          <ul class="flex flex-row list-none ml-auto">
            <li class="nav-item">
              <a
                class="social-icon px-3 py-2 hover:opacity-75"
                href="#facebook"
              >
                <i class="fab fa-facebook fa-fw fa-gradient" />
              </a>
            </li>
            <li class="nav-item">
              <a class="social-icon px-3 py-2 hover:opacity-75" href="#twitter">
                <i class="fab fa-twitter fa-fw fa-gradient" />
              </a>
            </li>
            <li class="nav-item">
              <a
                class="social-icon px-3 py-2 hover:opacity-75"
                href="#telegram"
              >
                <i class="fab fa-telegram fa-fw fa-gradient" />
              </a>
            </li>
            <li class="nav-item">
              <a class="social-icon px-3 py-2 hover:opacity-75" href="#youtube">
                <i class="fab fa-youtube fa-fw fa-gradient" />
              </a>
            </li>
            <li class="nav-item">
              <a class="social-icon px-3 py-2 hover:opacity-75" href="#discord">
                <i class="fab fa-discord fa-fw fa-gradient" />
              </a>
            </li>
            <li class="nav-item">
              <a class="social-icon px-3 py-2 hover:opacity-75" href="#reddit">
                <i class="fab fa-reddit fa-fw fa-gradient" />
              </a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <nav class="custom-nav w-full bg-transparent">
      <div class="container mx-auto flex items-center justify-between h-full">
        <!-- Header logo -->
        <a
          href="/"
          class="navbrand d-none d-lg-inline-block"
          rel="nofollow"
          ><img src="~/assets/images/logo.png" height="50" class="mr-3"
        /></a>

        <!-- Mobile toggle -->
        <div class="md:hidden">
          <button @click="drawer">
            <svg
              class="h-8 w-8 fill-current text-black"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              viewBox="0 0 24 24"
              stroke="white"
            >
              <path d="M4 6h16M4 12h16M4 18h16"></path>
            </svg>
          </button>
        </div>

        <!-- Navbar -->
       
        <div class="nav-links hidden md:flex  flex-col md:flex-row text-center">
          <div class="flex-fill"><a href="/" class="px-3">Home</a></div>
          <div class="flex-fill"><a href="/" class="px-3" target="_blank">Tokenomics</a></div>
          <div class="flex-fill"><a href="/Roadmap" class="px-3">Roadmap<div class="new"></div></a></div>
          <div class="flex-fill"><a href="/buy" class="px-3">Buy Now</a></div>
        </div>
        
        <!-- Dark Background Transition -->
        <transition
          enter-class="opacity-0"
          enter-active-class="ease-out transition-medium"
          enter-to-class="opacity-100"
          leave-class="opacity-100"
          leave-active-class="ease-out transition-medium"
          leave-to-class="opacity-0"
        >
          <div
            @keydown.esc="isOpen = false"
            v-show="isOpen"
            class="z-10 fixed inset-0 transition-opacity"
          >
            <div
              @click="isOpen = false"
              class="absolute inset-0 bg-black opacity-50"
              tabindex="0"
            ></div>
          </div>
        </transition>

        <!-- Drawer Menu -->
        <aside
          class="
            p-5
            transform
            top-0
            left-0
            w-64
            bg-white
            fixed
            h-full
            overflow-auto
            ease-in-out
            transition-all
            duration-300
            z-30
          "
          :class="isOpen ? 'translate-x-0' : '-translate-x-full'"
        >
          <div class="close">
            <button
              class="absolute top-0 right-0 mt-4 mr-4"
              @click="isOpen = false"
            >
              <svg
                class="w-6 h-6"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path d="M6 18L18 6M6 6l12 12"></path>
              </svg>
            </button>
          </div>

          <span
            @click="isOpen = false"
            class="flex w-full items-center p-4 border-b"
          >
            <img class="h-16" src="~/assets/images/logo.png" />
          </span>

          <ul class="divide-y font-sans">
            <li>
              <a href="#" @click="isOpen = false" class="my-4 inline-block"
                >Home</a
              >
            </li>
            <li>
              <a href="#" @click="isOpen = false" class="my-4 inline-block"
                >Tokenomics</a
              >
            </li>
            <li>
              <a href="#" @click="isOpen = false" class="my-4 inline-block"
                >Roadmap</a
              >
            </li>
            <li>
              <a href="#" @click="isOpen = false" class="my-4 inline-block"
                >Buy Now</a
              >
            </li>
          </ul>

          <div class="follow">
            <p class="italic font-sans text-sm">follow us:</p>
            <div class="social flex space-x-5 mt-4">
              <a href="#">
                <svg
                  aria-hidden="true"
                  focusable="false"
                  data-prefix="fab"
                  data-icon="twitter"
                  class="h-5 w-5 fill-current text-gray-600"
                  role="img"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 512 512"
                >
                  <path
                    fill="currentColor"
                    d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"
                  ></path>
                </svg>
              </a>
              <a href="#">
                <svg
                  aria-hidden="true"
                  focusable="false"
                  data-prefix="fab"
                  data-icon="facebook-f"
                  class="h-5 w-5 fill-current text-gray-600"
                  role="img"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 320 512"
                >
                  <path
                    fill="currentColor"
                    d="M279.14 288l14.22-92.66h-88.91v-60.13c0-25.35 12.42-50.06 52.24-50.06h40.42V6.26S260.43 0 225.36 0c-73.22 0-121.08 44.38-121.08 124.72v70.62H22.89V288h81.39v224h100.17V288z"
                  ></path>
                </svg>
              </a>
              <a href="#">
                <svg
                  aria-hidden="true"
                  focusable="false"
                  data-prefix="fab"
                  data-icon="instagram"
                  class="h-5 w-5 fill-current text-gray-600"
                  role="img"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 448 512"
                >
                  <path
                    fill="currentColor"
                    d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"
                  ></path>
                </svg>
              </a>
              <a href="#">
                <svg
                  aria-hidden="true"
                  focusable="false"
                  data-prefix="fab"
                  data-icon="youtube"
                  class="h-5 w-5 fill-current text-gray-600"
                  role="img"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 576 512"
                >
                  <path
                    fill="currentColor"
                    d="M549.655 124.083c-6.281-23.65-24.787-42.276-48.284-48.597C458.781 64 288 64 288 64S117.22 64 74.629 75.486c-23.497 6.322-42.003 24.947-48.284 48.597-11.412 42.867-11.412 132.305-11.412 132.305s0 89.438 11.412 132.305c6.281 23.65 24.787 41.5 48.284 47.821C117.22 448 288 448 288 448s170.78 0 213.371-11.486c23.497-6.321 42.003-24.171 48.284-47.821 11.412-42.867 11.412-132.305 11.412-132.305s0-89.438-11.412-132.305zm-317.51 213.508V175.185l142.739 81.205-142.739 81.201z"
                  ></path>
                </svg>
              </a>
            </div>
          </div>
        </aside>
      </div>
    </nav>
    <div class="container mx-auto">
      <div class="flex items-center header-row">
        <div class="flex-fill w-full">
          <p class="text-light mb-5">Welcome to</p>
          <h1 class="bignumbers mb-5">Raging Phoenix (RPX)</h1>
          <p class="text-white mb-5">The Raging Phoenix Token is a community driven, fair launched DeFi Token. Three simple
            functions <br>occur during each trade: Reflection, LP Acquisition, and Burn.</p>
          <!-- <div class="widget-container mb-10 w-max text-white">
            <p>Presale Wallet: </p>
          </div> -->
          <div>
             <a href="#" class="btn btn-success px-6 py-4 mr-2 text-white rounded-lg"
            target="_blank">Live Chart</a>
            <a href="/buy" class="btn px-6 py-4 border border-white text-white rounded-lg">Buy Now <i class="fas fa-shopping-cart"></i></a>
          </div>
        </div>
      </div>
      <div class="flex lg:text-center flex-col lg:flex-row header-stats relative z-10">
        <div class="flex-fill w-100 py-3">
          <p class="mb-0 h3 text-white">0x213568C69798359b7f1f9807D5d0C5Dd531138cb</p>
          <p class="mb-0 text-light text-xs">Presale Wallet</p>
        </div>
        <div class="flex-fill w-100 py-3">
          <p class="mb-0 h3 text-white">1 BNB = 110,000,000,000</p>
          <p class="mb-0 text-light text-xs">Private Sale Price</p>
        </div>
        <div class="flex-fill w-100 py-3">
          <p class="mb-0 h3 text-white">1 BNB = 100,000,000,000</p>
          <p class="mb-0 text-light text-xs">Pancake Swap Price</p>
        </div>
        <div class="flex-fill w-100 py-3">
          <p class="mb-0 h3 text-white">1,000,000,000,000,000</p>
          <p class="mb-0 text-light text-xs">Initial Supply</p>
        </div>
        
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
      config: {
        num: 400

      }
    };
  },
  methods: {
    drawer() {
      this.isOpen = !this.isOpen;
    },
  },
  watch: {
    isOpen: {
      immediate: true,
      handler(isOpen) {
        if (process.client) {
          if (isOpen) document.body.style.setProperty("overflow", "hidden");
          else document.body.style.removeProperty("overflow");
        }
      },
    },
  },
  mounted() {
    document.addEventListener("keydown", (e) => {
      if (e.keyCode == 27 && this.isOpen) this.isOpen = false;
    });
  },
};
</script>
<style lang="sass" scoped>
header
  background-color: #1b1e25

  &:before, &:after
    content: " "
    position: absolute
    left: 0
    top: 0
    bottom: 0
    width: 100%

  &:after
    z-index: 2
    background: linear-gradient(180deg,transparent 27%,#1f232b),radial-gradient(farthest-corner,transparent 0,#1f232b 100%)

  &:before
    background: url(~/assets/images/earth.png) bottom -100px center no-repeat
    z-index: 1
  .header-row
    position: relative
    min-height: 600px !important
    z-index: 5 !important
    padding-top: 100px

  .social
    &-header
      height: 45px
      font-size: 10px

    &-icon
      font-size: 20px

      i
        color: #FF7E52

  .custom-nav
    position: relative
    height: 80px
    z-index: 1000!important
    background-color: transparent
    background-color: hsla(0,0%,100%,.01)
    border-bottom: 1px solid hsla(0,0%,100%,.03)

    .nav-links
      a
        font-size: 1rem
        position: relative
        color: hsla(0,0%,100%,.6666666666666666)
        display: inline-block
        min-width: 100px
        height: 80px
        line-height: 80px
        transition: all .1s ease-in-out

        &:before
          content: " "
          position: absolute
          height: 2px
          left: 0
          width: 0
          border-bottom: 3px solid #fff
          bottom: 0
          transition: all .2s ease-in-out

      &:hover
        &:before
          &:hover
            border-bottom: 3px solid #fff
            width: 100%

.flex-fill
  flex: 1 1 auto !important

.new
  display: inline-block
  position: absolute
  border-radius: 50%
  width: 7px
  height: 7px
  top: 50%
  margin-top: -10px
  right: 5px
  background-color: #FF7E52
  animation: pulse-danger 2s infinite

@keyframes pulse-danger
  0%
    box-shadow:0 0 0 0 #FF7E52
  to
    box-shadow:0 0 0 15px transparent

.text-light
  color: #ced4da !important

.bignumbers
  color: white
  font:
    size: 50px
    weight: 600
    family: 'Atmospheric'
  line-height: 1em

.btn-success
  border-color: #2dce89
  background-image: linear-gradient(89deg,#ff7854,#ffaf48)

.particles-js
  position: absolute
  top: 0
  bottom: 0
  width: 100%
  height: 100%
  z-index: 0

.widget-container
  padding: 5px 10px 5px 10px
  background-color: #1e2228
  border-radius: 5px 5px 5px 5px
</style>