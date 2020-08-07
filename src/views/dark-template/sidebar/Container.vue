<template>
  <v-card
    color="grey darken-3"
    dark
  >
    <v-card-text>
      <avatar />
      <div class="text-sm-center mb-4 mt-3">
        <h1>
          <span class="light-blue--text text--lighten-3">Geo Nicolaidis</span>
        </h1>
        <span>
          AWS Certified Solutions Architect
        </span>
      </div>

      <sidebar-section :options="sections.info" />
      <sidebar-section :options="sections.socials" />
      <sidebar-section :options="sections.hobbies">
        <template v-slot:item="{item}">
          <v-chip>
            <v-avatar>
              <v-icon>
                {{ item.icon }}
              </v-icon>
            </v-avatar>
            {{ item.text }}
          </v-chip>
        </template>
      </sidebar-section>
      <sidebar-section :options="sections.languages">
        <template v-slot:items="{items}">
          <v-container pa-0>
            <v-layout
              wrap
              class="text-xs-center"
            >
              <template
                v-for="(item, i) in items"
              >
                <v-flex
                  :key="i"
                  md3
                  sm4
                  xs6
                >
                  <v-progress-circular
                    rotate="360"
                    size="65"
                    width="2"
                    :value="item.value"
                    color="white"
                    class="ma-2"
                  >
                    {{ item.text }}
                  </v-progress-circular>
                </v-flex>
              </template>
            </v-layout>
          </v-container>
        </template>
      </sidebar-section>
    </v-card-text>
  </v-card>
</template>

<script>
import Avatar from '@/views/dark-template/sidebar/Avatar'
import SidebarSection from '@/views/dark-template/sidebar/Section'
export default {
  name      : 'Sidebar',
  components: { SidebarSection, Avatar },
  data () {
    return {
      sections: {
        info: {
          title: 'INFO',
          items: [
            {
              name: 'Email',
              icon: 'mdi-email',
              text: 'geo@znd.life',
            },
            {
              name: 'Website',
              icon: 'mdi-web',
              text: 'geonicolaidis.com',
            },
            {
              name: 'Birthdate',
              icon: 'mdi-cake-variant',
              text: 'Jun 27, 1984',
            },
            {
              name: 'Location',
              icon: 'mdi-map-marker',
              text: 'Limassol, Cyprus',
            },
          ],
        },
        socials: {
          title: 'SOCIALS',
          items: [
            {
              icon: 'mdi-github-circle',
              text: 'github.com/GeoNicol',
              link: 'https://github.com/GeoNicol',
            },
            {
              icon: 'mdi-linkedin-box',
              text: 'linkedin.com/in/geo-nicolaidis',
              link: 'https://www.linkedin.com/in/geo-nicolaidis',
            },           
            {
              icon: 'mdi-instagram',
              text: 'instagram.com/geo_nicolaidis',
              link: 'https://www.instagram.com/geo_nicolaidis',
            },
          ],
        },
        hobbies: {
          title: 'HOBBIES',
          items: [
            {
              icon: 'mdi-bike',
              text: 'Cycling',
            },
            {
              icon: 'mdi-image-filter-hdr',
              text: 'Nature',
            },
            {
              icon: 'mdi-auto-fix',
              text: 'Hacking Things',
            },
            {
              icon: 'mdi-teach',
              text: 'Teaching',
            },
            {
              icon: 'mdi-soccer',
              text: 'Sports',
            },
            {
              icon: 'mdi-music',
              text: 'Music',
            },
            {
              icon: 'mdi-cookie',
              text: 'Cooking',
            },
            {
              icon: 'mdi-account-group',
              text: 'Leadership',
            },            
            {
              icon: 'mdi-book-open-page-variant',
              text: 'Books',
            },            
          ],
        },
        languages: {
          title: 'LANGUAGES',
          items: [
            {
              text : 'English',
              value: 100,
            },
            {
              text : 'Greek',
              value: 100,
            },
            {
              text : 'Spanish',
              value: 35,
            },
            {
              text : 'Italian',
              value: 25,
            },
          ],
        },
      },
    }
  },
}
</script>

<style scoped>
.sidebar{
    background: #2e2e2e;
}
</style>
