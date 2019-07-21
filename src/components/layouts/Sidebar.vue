<template>
  <v-card class="menu-list" style="width: 400px">

    <v-list two-line>
      <template v-for="(item, index) in items">
        <v-subheader
                v-if="item.header"
                :key="item.header"
        >
          {{ item.header }}
        </v-subheader>

        <v-divider
                v-else-if="item.divider"
                :key="index"
                :inset="item.inset"
        ></v-divider>

        <v-list-tile
                v-else
                :key="item.title"
                avatar
                @click=""
        >
          <v-list-tile-avatar>
            <img :src="item.avatar">
          </v-list-tile-avatar>

          <v-list-tile-content>
            <v-list-tile-title v-html="item.title"></v-list-tile-title>
            <v-list-tile-sub-title v-html="item.subtitle"></v-list-tile-sub-title>
          </v-list-tile-content>
        </v-list-tile>
      </template>
    </v-list>
  </v-card>
</template>

<script>
    export default {
        props: [
            "sidebar"
        ],
        name: "SideBarMenu",
        data () {
            return {
                items: [
                    {header: 'Меню'},
                    {
                        avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
                        title: 'Моя страница',
                    },
                    {divider: true, inset: true},
                    {
                        avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
                        title: 'Новости',
                    },
                    {divider: true, inset: true},
                    {
                        avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
                        title: 'Диалоги',
                    }
                ]
            }
        }
    }
</script>

<style scoped>
  .menu-list {
    margin-top: 60px;
  }
</style>