<template>
    <div class="cont">
        <h1>Descubre lo que hace este inútil botón</h1>
        <button @click="Contar()" @mouseenter="onHover()">Clickeame!</button>
        <div> <h4> Haz clickeado {{clicks}}</h4></div>
        <div> <h4> Haz pasado sobre el botón {{sobre_boton}} veces</h4></div>
    </div>
</template>

<script>

export default {
  name: 'contador',
  data() {
    return {
        clicks:0,
        sobre_boton:0
    };
  },
  mounted(){
        if(localStorage.clicks){
            this.clicks= localStorage.clicks;
        }
        if(localStorage.sobre_boton){
            this.sobre_boton= localStorage.sobre_boton;
        }
  },
  methods: {
      Contar(){
          this.clicks++;
          localStorage.clicks = this.clicks
      },
      onHover(){
          this.sobre_boton++;
          localStorage.sobre_boton = this.sobre_boton
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
