<template>
  <div>
    <v-layout row justify-center>
      <v-dialog v-model="dialog" max-width="600px">
        <v-card>

          <v-form
                  ref="form"
                  v-model="valid"
                  lazy-validation
                  style="padding: 30px 10px 10px 0;"
          >

            <v-form-title class="flex justify-center" style="width: 100%">
              <div class="headline text-lg-center">
                {{ formTitle }}
              </div>
            </v-form-title>

            <v-card-text>
              <v-text-field
                      v-model="name"
                      :counter="10"
                      :rules="nameRules"
                      label="Name"
                      required
              ></v-text-field>

              <v-text-field
                      v-model="email"
                      :rules="emailRules"
                      label="E-mail"
                      required
              ></v-text-field>

              <v-checkbox
                      v-model="checkbox"
                      :rules="[v => !!v || 'You must agree to continue!']"
                      label="Do you agree?"
                      required
              ></v-checkbox>

              <v-btn
                      :disabled="!valid"
                      color="primary"
                      @click="validate"
              >
                {{ btnTextLogin }}
              </v-btn>

              <v-btn
                      @click="hideForm"
              >
                {{ textBtnCancel }}
              </v-btn>
            </v-card-text>

          </v-form>

        </v-card>
      </v-dialog>
    </v-layout>
  </div>
</template>

<script>
    export default {
        name: "LoginForm",
        props: ['dialog'],
        data: () => ({
            textBtnCancel: 'Отмена',
            btnTextLogin: 'Войти',
            formTitle: 'Авторизация',
            valid: true,
            name: '',
            nameRules: [
                v => !!v || 'Это обязательное поле',
                v => (v && v.length <= 10) || 'Name must be less than 10 characters'
            ],
            email: '',
            emailRules: [
                v => !!v || 'Это обязательно поле',
                v => /.+@.+/.test(v) || 'E-mail должен быть корректным'
            ],
            select: null,
            checkbox: false
        }),

        methods: {
            validate() {
                if (this.$refs.form.validate()) {
                    this.snackbar = true
                }
            },
            hideForm() {
                this.$emit('hideForm');
            }
        }
    }
</script>

<style scoped>

</style>