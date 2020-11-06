<template>
  <div id="MostrarDatos">
    <div>
      <b-navbar type="dark" variant="secondary">
        <b-navbar-brand>Administración de prestamos</b-navbar-brand>

        <b-collapse id="nav-text-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-text>Mis registros</b-nav-text>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
      <br />
    </div>

    <div id="Info" style="height: 650px; overflow-y: scroll">
      <b-alert
        show
        v-if="Mensaje.MostrarMensaje"
        :variant="Mensaje.Color"
        class="Alerta"
        >{{ Mensaje.Texto }}
        <br />
      </b-alert>

      <div v-for="Datos in Info" v-bind:key="Datos._id">
        <b-card
          header=""
          header-tag="header"
          footer=""
          footer-tag="footer"
          border-variant="info"
        >
          <template #header> Datos del deudor </template>

          <form>
            <div class="form-row">
              <div class="form-group col-md-6">
                <label for="DUI">DUI</label>
                <input
                  type="text"
                  class="form-control"
                  id="DUI"
                  :placeholder="Datos.DUI"
                  disabled
                />
              </div>
              <div class="form-group col-md-6">
                <label for="NombreCompleto">Nombre completo</label>
                <input
                  type="text"
                  class="form-control"
                  id="NombreCompleto"
                  :placeholder="Datos.Nombres + ' ' + Datos.Apellidos"
                  disabled
                />
              </div>
            </div>
            <div class="form-row">
              <div class="form-group col-md-6">
                <label for="">Monto otorgado</label>
                <b-input-group prepend="$">
                  <input
                    type="text"
                    class="form-control"
                    disabled
                    :placeholder="Datos.Monto_Prestado"
                  />
                </b-input-group>
              </div>
              <div class="form-group col-md-6">
                <label for="">Intereses a cobrar</label>
                <b-input-group prepend="$">
                  <input
                    type="text"
                    class="form-control"
                    disabled
                    :placeholder="Datos.Intereses"
                  />
                </b-input-group>
              </div>
            </div>
            <div class="form-row">
              <div class="form-grouo col-md-6">
                <label for="Plazo">Plazo otorgado</label>
                <b-input-group append="días">
                  <input
                    id="Plazo"
                    type="text"
                    class="form-control"
                    :placeholder="Datos.Plazo_Pago"
                    disabled
                  />
                </b-input-group>
              </div>
            </div>
          </form>
          <template #footer>
            <span>
              <b>Fecha de creación: </b>
              <b-badge pill variant="danger">{{ Datos.Fecha }}</b-badge></span
            >
          </template>
        </b-card>
        <br />
      </div>
      <br />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    Info: Array,
    Mensaje: Object,
  },
};
</script>

<style>
</style>