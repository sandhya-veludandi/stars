<template>
  <!-- tsParticles Repository: https://github.com/matteobruni/tsparticles -->
  <!-- tsParticles Website: https://particles.js.org -->
  <Particles
    id="tsparticles"
    :options="options"
    :particlesInit="particlesInit"
  />
</template>

<script lang="ts">
import type { Engine } from "tsparticles-engine";
import { loadSlim } from "tsparticles-slim";
//import { loadFull } from "tsparticles";
export default {
  data() {
    return {
        options: {
            particles: {
                number: {
                    density: {
                    enable: false,
                    value_area: 1500,
                    },
                    value: 100,
                },
                shape: {
                    type: 'star',
                    stroke: {
                    width: 0.8,
                    color: '#45f0df'
                    }
                },
                line_linked: {
                    enable: false, 
                    distance: 90, 
                    opacity: 1, 
                    width: 1.5
                },
                move: {
                    enable: true,
                    direction: 'right',
                    random: true,
                    straight: true,
                    speed: 0.25,
                    outMode: 'out'
                },
                size: {
                    anim: {
                    speed: 100, 
                    size_min: 0.03
                    },
                    random: true,
                    value: 1.25
                },
                opacity: {
                    anim: {
                        enable: true,
                        speed: 1.25,
                        opacity_min: 0.3
                    },
                    value: 1,
                    random: true
                }
            },
            background: {
                color: '#111d4A'
            },
            interactivity: {
                detectsOn: 'canvas',
                events: {
                    onHover: {
                    enable: true,
                    mode: 'grab',
                    },
                    onClick: {
                    enable: true,
                    mode: 'push',
                    }
                },
                modes: {
                    grab: {
                    line_linked: {
                        opacity: 0.85
                    },
                    distance: 90
                    },
                    push: {
                        particles_nb: 1
                    }
                }
            },
            detectRetina: true
        }
    
    };
  },
  methods: {
    async particlesInit(engine: Engine) {
      await loadSlim(engine);
    },
  },
};
</script>