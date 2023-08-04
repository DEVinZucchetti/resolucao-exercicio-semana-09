<template>
  <Header />
  <FormularioNovoMedicamento @cadastrar="cadastrarMedicamento" />
</template>

<script>
import Header from "./components/Header.vue"
import FormularioNovoMedicamento from "./components/FormularioNovoMedicamento/index.vue"

export default {
  components: {
    Header,
    FormularioNovoMedicamento
  },
  methods: {
    cadastrarMedicamento(){
      
    }
  }
}
</script>

<style scoped>

</style>
