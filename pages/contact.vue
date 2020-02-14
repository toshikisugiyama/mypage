<template>
  <main class="contact">
    <v-container tag="section" class="contact__content">
      <v-row class="contact__content__row">
        <v-col v-text="title.toUpperCase()" class="contact__content__row__title" cols="12" tag="h1" />
      </v-row>
      <v-row>
        <v-col cols="12">
          <v-form dark netlify>
            <v-col v-for="(form, index) in forms" :key="index" cols="12">
              <v-text-field
                v-model="form.model"
                :label="form.label"
                required
              />
            </v-col>
            <v-btn>
              {{ button }}
            </v-btn>
          </v-form>
        </v-col>
      </v-row>
    </v-container>
  </main>
</template>

<script>
export default {
  data () {
    return {
      title: 'contact',
      button: '送信',
      forms: [
        {
          label: 'お名前',
          model: ''
        },
        {
          label: 'Eメール',
          model: ''
        },
        {
          label: '内容',
          model: ''
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.contact{
  padding: $header-height $side-space;
  background-color: $main-color;
  min-height: 100vh;
  color: $light-color;
  &__content {
    &__row {
      &__title {
        text-align: center;
        padding: 0 $side-space;
        @include title;
      }
    }
  }
}
</style>

