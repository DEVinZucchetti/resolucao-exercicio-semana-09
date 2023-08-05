<template>
  <Header />
  <FormularioNovoMedicamento @cadastrar="AdicionarMedicamento" />
  <div class="container">
    <CardMedicamento 
      @favoritar="FavoritarMedicamento" 
      nome="Dipirona" 
      laboratorio="Clamed" 
      preco="5,00" 
      id="1" 
    />
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';
import Header from "./components/Header.vue"
import FormularioNovoMedicamento from "./components/FormularioNovoMedicamento/index.vue"
import CardMedicamento from "./components/CardMedicamento/index.vue"

export default {
  components: {
    Header,
    FormularioNovoMedicamento,
    CardMedicamento
  },
  data() {
    return {
      listaMedicamentos: []
    }
  },
  methods: {
    AdicionarMedicamento(nome, laboratorio, preco) {

      if (nome == "" || laboratorio == "" || preco == 0) {
        alert("Preencha todos os dados")
        return
      }

      const novoMedicamento = {
        id: uuidv4(),
        nome: nome,
        laboratorio: laboratorio,
        preco: preco,
        favorito: false
      }

      this.listaMedicamentos.push(novoMedicamento)
    },
    FavoritarMedicamento(id) {
      debugger
      alert(id)
    }
  }
}
</script>

<style scoped>
.container {
  display: flex;
  widows: 100vw;
  padding: 1em;
}
</style>
