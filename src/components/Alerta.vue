<template>
  <div id="Alerta">
    <div>
      <b-alert
        show
        v-if="Alerta.Mostrar_Alerta"
        :variant="Alerta.Color"
        class="Alerta"
        >{{ Alerta.Texto }}
        <br />
        <b-button variant="outline-success" href="#Entrada" size="sm">
          Incluir entrada</b-button
        >
      </b-alert>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    Alerta: Object,
  },
};
</script>

<style>
.Alerta {
  margin-top: 15px;
  text-align: center;
}
</style>