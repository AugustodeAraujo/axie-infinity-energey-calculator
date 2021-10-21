<template>
  <div class="max-h-screen min-h-screen bg-gray-900">
    <Container>
      <div class="flex items-center justify-center h-screen">
        <div>
          <div class="-mb-6 flex justify-center">
            <img class="z-10" src="@/assets/images/axie-logo.png" alt="" />
          </div>
          <div
            class="
              bg-gray-800
              p-10
              rounded-md
              h-auto
              w-72
              md:w-96
              filter
              drop-shadow-lg
            "
          >
            <p class="text-center font-bold text-yellow-400 text-4xl uppercase">
              Partida {{ arenaCount }}
            </p>
            <div class="mt-4 mb-2 border-b border-gray-600"></div>
            <p class="text-center font-bold uppercase text-gray-600">
              Round {{ roundCount }} - Energia do Inimigo
            </p>
            <div class="mt-6 flex justify-center">
              <div
                class="
                  bg-gray-900
                  w-32
                  h-32
                  rounded
                  flex
                  items-center
                  justify-center
                "
              >
                <p class="font-mono text-7xl text-yellow-300 font-black">
                  {{ energyCount }}
                </p>
              </div>
            </div>

            <div class="flex justify-center my-4 space-x-4">
              <button @click="increaseEnergy">
                <img
                  class="h-16"
                  src="@/assets/images/plusbtn.png"
                  alt="Plus Button"
                />
              </button>

              <button @click="decreaseEnery">
                <img
                  class="h-16"
                  src="@/assets/images/minusbtn.png"
                  alt="Minus Button"
                />
              </button>
            </div>

            <div class="flex justify-center">
              <button
                class="
                  bg-blue-500
                  px-4
                  py-2
                  w-full
                  text-white
                  rounded
                  font-bold
                "
                @click="nextRound"
              >
                Próximo Round
              </button>
            </div>

            <div class="flex justify-center">
              <button
                class="
                  mt-2
                  bg-yellow-400
                  px-4
                  py-2
                  w-full
                  text-white
                  rounded
                  font-bold
                "
                @click="newArena"
              >
                Nova Partida
              </button>
            </div>

            <div class="flex justify-center">
              <button
                class="
                  mt-2
                  bg-pink-400
                  px-4
                  py-2
                  text-white
                  rounded
                  font-bold
                  text-sm
                "
                @click="resetArena"
              >
                Reset Arena
              </button>
            </div>
            <p class="text-sm text-center mt-8 -mb-6 font-bold text-gray-600">
              v1.0
            </p>
          </div>
          <div class="text-center mt-10 text-gray-700 font-bold">
            made by @haterhonesto
          </div>
          <div class="text-center text-xs mt-2 text-gray-700">
            Se essa ferramente está sendo útil para você, <br />considere ajudar
            o projeto com qualquer <br />
            quantidade de <strong>SLP</strong>, <strong>WETH</strong> ou
            <strong>AXS</strong>.
          </div>
        </div>
      </div>
    </Container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      energyCount: 3,
      arenaCount: 1,
      roundCount: 1,
    }
  },

  methods: {
    nextRound() {
      this.roundCount += 1
      this.energyCount += 2
    },
    newArena() {
      this.roundCount = 1
      this.arenaCount += 1
      this.energyCount = 3
    },
    increaseEnergy() {
      this.energyCount += 1
    },
    decreaseEnery() {
      if (this.energyCount > 0) {
        this.energyCount -= 1
      }
    },
    resetArena() {
      this.arenaCount = 1
      this.roundCount = 1
      this.energyCount = 3
    },
  },
}
</script>
