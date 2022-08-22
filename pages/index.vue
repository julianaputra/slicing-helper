<template>
  <main>
    <div class="container pt-5">
      <h1 class="h2">
        Slicing Helper
      </h1>
      <p>Tools untuk meninkatkan desain presisi kamu ketika slicing desain dari figma</p>
      <hr>
      <b-form>
        <b-row>
          <b-col lg="6">
            <b-form-group
              id="fieldset-email"
              label="Figma Font Size"
              label-for="input-email"
              description="Font size dasar pada figma (biasanya 18px)."
            >
              <b-input-group append="px">
                <b-form-input
                  id="input-email"
                  v-model="form.figmaFont"
                  type="number"
                />
              </b-input-group>
            </b-form-group>
          </b-col>
          <b-col lg="6">
            <b-form-group
              id="fieldset-email"
              label="Web Font Size"
              label-for="input-email"
              description="Font size dasar pada web (biasanya 16px)."
            >
              <b-input-group append="px">
                <b-form-input
                  id="input-email"
                  v-model="form.webFont"
                  type="number"
                />
              </b-input-group>
            </b-form-group>
          </b-col>
        </b-row>
        <hr>
        <b-form-group
          id="fieldset-email"
          label="Ukuran Elemen pada Figma"
          label-for="input-email"
          description="Masukkan ukuran elemen pada figma."
        >
          <b-input-group append="px">
            <b-form-input
              id="input-email"
              v-model="form.figmaSize"
              autofocus
              type="number"
            />
          </b-input-group>
        </b-form-group>

        <b-card class="mb-3">
          <h6>Ukuran Elemen pada Web</h6>
          <h4>{{ webSize }} px</h4>
        </b-card>

        <b-card>
          <h6>Ukuran Elemen pada Web (dalam rem)</h6>
          <h4>{{ webSizeRem }} rem</h4>
        </b-card>
      </b-form>
    </div>
  </main>
</template>

<script>
export default {
  data () {
    return {
      form: {
        figmaFont: 18,
        webFont: 16,
        figmaSize: null
      }
    }
  },
  computed: {
    webSize () {
      return this.form.figmaSize * this.form.webFont / this.form.figmaFont
    },
    webSizeRem () {
      return this.webSize / this.form.webFont
    }
  }
}
</script>

<style lang="scss">
main {
  max-width: 600px;
  margin: auto;
  min-height: calc(100vh - 40px);
}
</style>
