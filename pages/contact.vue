<template>
  <main class="contact">
    <v-container tag="section" class="contact__content">
      <v-row class="contact__content__row">
        <v-col v-text="title.toUpperCase()" class="contact__content__row__title" cols="12" tag="h1" />
      </v-row>
      <v-row class="form">
        <v-col cols="12" class="form__wrapper">
          <v-form>
            <v-col
              v-for="(form, index) in forms"
              :key="index"
              class="v-form__item"
              cols="12"
            >
              <v-text-field
                v-if="index < 2"
                v-model="form.model"
                :label="form.label"
                :type="form.type"
                dark
                required
              />
              <v-textarea
                v-else
                v-model="form.model"
                :label="form.label"
                dark
                required
              />
            </v-col>
            <v-col cols="12" class="v-form__item">
              <v-btn
                :disabled="isEmpty"
                @click="submit"
                dark
                outlined
              >
                {{ button }}
              </v-btn>
            </v-col>
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
          type: 'text',
          model: ''
        },
        {
          label: 'Eメール',
          type: 'email',
          model: ''
        },
        {
          label: '内容',
          model: ''
        }
      ]
    }
  },
  computed: {
    name () {return this.forms[0].model},
    email () {return this.forms[1].model},
    content () {return this.forms[2].model},
    isEmpty () {
      if (this.name !== "" && this.email !== "" && this.content !== "") {
        return false
      }
      return true
    }
  },
  methods: {
    async submit () {
      const params = new FormData()
      params.append('form-name', 'contact')
      params.append('name', this.name)
      params.append('email', this.email)
      params.append('content', this.content)
      await this.$axios.$post(window.location.origin, params)
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.contact{
  padding: $header-height 0 0;
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
    .form {
      &__wrapper {
        .v-form {
          &__item {
            padding: 0;
          }
          &__item:nth-child(3) {
            margin-bottom: 40px;
          }
          &__item:last-of-type {
            display: flex;
            justify-content: center;
          }
        }
      }
    }
  }
}
</style>

