<template>
  <section class="src-components-final">
    <h1>Final Daniel Pisa</h1>
    <div>
      <span> Color: <input type="text" v-model="color" /> </span>
      <span> Fondo: <input type="text" v-model="fondo" /> </span>
      <span> Size: <input type="text" v-model="size" /> </span>
    </div>
    <hr />
    <input type="text" v-model.trim="texto" :style="cambiarEstilo()" />
    
    <p>Cantidad de palabras: {{ contarPalabras }}</p>

    <hr />
<table class="table">
        <div class="table-responsive">
          <table class="table table-dark">
            <tr>
              <th>Nro pregunta</th>
              <th>Respuesta</th>
            </tr>
            <tr v-for="(pregunta,index) in preguntas" :key="index" :style="{color: 'black', backgroundColor:'silver'}">
              <td>{{ pregunta.numero }}</td>
              <td>{{ pregunta.respuesta }}</td>
            </tr>
          </table>
       </div>
      </table>
  </section>
</template>

<script lang="js">

  export default  {
    name: 'src-components-final',
    props: [],
    mounted () {

    },
    data () {
      return {
        color: '',
        fondo: '',
        size: '',
        texto: '',
        preguntas : [
                    { numero: 1, respuesta: ['B'] },
                    { numero: 2, respuesta: ['C'] },
                    { numero: 3, respuesta: ['B'] },
                    { numero: 4, respuesta: ['D'] },
                    { numero: 5, respuesta: ['D'] },
                    ]
      
      }
    },
    methods: {
cambiarEstilo() {
        return {
          color: this.color,
          backgroundColor: this.fondo,
          fontSize: this.size + "px"
        };
    }
    },
    computed: {
    contarPalabras() {
      let cant = this.texto.split(' ').length;
		return this.texto == "" ? 0 : cant
	}
}
}
</script>

<style scoped lang="css"></style>
