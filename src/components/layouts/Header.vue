<template>
  <div>
    <v-toolbar app dark class="primary">

      <v-navigation-drawer
              v-model="drawer"
              light
              absolute
              temporary
              style="height: 100vh"
      >
        <v-list class="pa-1">
          <v-list-tile avatar>
            <v-list-tile-avatar>
              <img src="https://randomuser.me/api/portraits/men/85.jpg">
            </v-list-tile-avatar>

            <v-list-tile-content>
              <v-list-tile-title>{{ userTitle }}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>

        <v-list class="pt-0" dense>
          <v-divider></v-divider>

          <v-list-tile
                  v-for="item in items"
                  :key="item.title"
                  @click=""
          >
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>

            <v-list-tile-content>
              <v-list-tile-title>{{ item.title }}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer>

      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title v-text="'Inverse'"></v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>search</v-icon>
      </v-btn>
      <v-toolbar-items>
        <v-btn @click="showLoginForm" flat>{{ btnText }}</v-btn>
      </v-toolbar-items>
    </v-toolbar>

    <login-form :dialog="dialog" @hideForm="hideModal"></login-form>
  </div>
</template>

<script>
    import LoginForm from '../LoginForm.vue';

    export default {
        name: "Header",
        components: {
            LoginForm
        },
        data() {
            return {
                btnText: 'Войти',
                drawer: false,
                dialog: false,
                items: [
                    { title: 'Home', icon: 'dashboard' },
                    { title: 'About', icon: 'question_answer' }
                ],
                userTitle: 'Кирилл Баранов'
            }
        },
        methods: {
            showLoginForm: function () {
                this.dialog = true;
            },
            hideModal: function () {
                this.dialog = false;
            }
        }
    }
</script>

<style scoped>

</style>