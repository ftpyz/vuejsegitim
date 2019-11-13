<template>
  <div>
    <p v-if="!BaslamaDurumu">
      Merhaba; Oyuna başlamak için adını yazarmısın
      <br />
      <input type="text" v-model="Oyuncu" />
      <button @click="OyunaBasla">Başla</button>
    </p>
    <p v-else>
      Merhaba;
      <strong>{{Oyuncu}}</strong> sayı tahmin oyununa hoş geldin. Aklımdan 1'den 10'a kadar bir sayı tuttum.
      <br />Hadi tahminini yaz ve eğlenmeye başlayalım.
      <br />
      <input type="text" v-model="OyuncuTahmini" />
      <button @click="TahminEt">Tahmin Et</button>
      <button @click="OyunReset">Tekrar Başla</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "Oyun",
  data: () => {
    return {
      Oyuncu: "",
      BaslamaDurumu: false,
      OyuncuTahmini: "",
      AklimdakiSayi: 0
    };
  },
  created() {
    this.AklimdakiSayi = Math.floor(Math.random() * 10);
  },
  methods: {
    OyunaBasla() {
      this.BaslamaDurumu = true;
    },
    OyunReset() {
      this.BaslamaDurumu = false;
      this.Oyuncu = "";
    },
    TahminEt() {
      if (this.AklimdakiSayi == this.OyuncuTahmini) {
        alert("Tebrik Ederim Aklımdaki Sayıyı Buldun");
        this.OyunReset();
      } else {
        alert(
          "Hayır aklımdaki sayı " +
            this.OyuncuTahmini +
            " değil.Devam et deneyerek bulabilirsin"
        );
      }
    }
  }
};
</script>