<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text>
      <content-section title="Who am I?">
        I am a results-oriented technologist with over 12 years of proven track record on designing, developing and implementing enterprise-class, scalable SaaS systems.
        <!-- Bring superior team-building and management expertise on process and automation improvements to enhance IT operations and software development practices. 
        A tendency to thrive in dynamic and fluid environments while remaining pragmatic and focused. -->
      </content-section>
      <content-section
        v-if="prouds"
        title="What am I proud of?"
      >
        <v-layout
          v-for="(proud, i) in prouds"
          :key="i"
        >
          <v-flex
            md1
            xs3
          >
            <v-icon right>
              {{ proud.icon }}
            </v-icon>
          </v-flex>
          <v-flex
            md11
            xs9
          >
            <p>
              <strong>{{ proud.text }}</strong><br>
              <small>{{ proud.source }}</small>
            </p>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="educations"
        title="Education"
      >
        <v-layout
          v-for="(education, i) in educations"
          :key="i"
        >
          <v-flex md4>
            {{ education.from }} - {{ education.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="education.title">{{ education.title }}</strong>
            <div v-if="education.location">
              <i>{{ education.location }}</i>
            </div>
            <div v-if="education.description">
              {{ education.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="skills"
        id="to-timeline"
        title="Skills"
      >
        <template slot="actions">
          (% are relative not absolute)
        </template>
        <v-layout wrap>
          <template
            v-for="(skill, i) in skills"
          >
            <v-flex
              v-if="skill.divider"
              :key="i"
              md12
              xs12
              mb-4
            />
            <v-flex
              v-else
              :key="i"
              md6
              xs12
            >
              <div
                class="mr-2 ml-2"
              >
                <div class="align-center">
                  <v-icon
                    small
                  >
                    {{ skill.icon }}
                  </v-icon>
                  {{ skill.title }}
                </div>
                <v-progress-linear
                  class="progress"
                  color="secondary"
                  height="3"
                  :value="skill.value"
                />
              </div>
            </v-flex>
          </template>
        </v-layout>
      </content-section>
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
    prouds: [
      {
        icon  : 'mdi-help-rhombus-outline',
        text  : 'Designed a City Hall',
        source: '(2008 Aradippou Cyprus)',
      },
      {
        icon  : 'mdi-library-music',
        text  : 'Certified as an AWS Solutions Architect',
        source: '(March 2020)',
      },
      {
        icon  : 'mdi-timer-sand',
        text  : 'Started my very own fashion brand during Covid-19',
        source: '(znd.life)',
      },
      {
        icon  : 'mdi-account-multiple',
        text  : 'PUblished an article on Medium',
        source: '(How I saved a company $22K per year on database costs)',
      },
    ],
    educations: [
      {
        from       : '2010',
        to         : '2012 ',
        title      : 'BSc, Information Technology Cum Laude',
        location   : 'DePaul University',
        description: 'Member of Upsilon Pi Epsilon',
      },
    ],
    skills: [
      {
        title: 'ColdFusion',
        icon : 'mdi-language-coldfusion',
        value: 75,
      },
      {
        title: 'JavaScript',
        icon : 'mdi-language-javascript',
        value: 70,
      },
      {
        title: 'Vue.js Framework',
        icon : 'mdi-vuejs',
        value: 73,
      },
      {
        title: 'MSSQL Server',
        icon : 'mdi-microsoft-access',
        value: 80,
      },
      { divider: true },
      {
        title: 'Docker',
        icon : 'mdi-docker',
        value: 70,
      },
      {
        title: 'CentOS Server',
        icon : 'mdi-linux',
        value: 80,
      },
      {
        title: 'Web Application Security',
        icon : 'mdi-shield-lock',
        value: 80,
      },
      {
        title: 'AWS Services',
        icon : 'mdi-test-tube',
        value: 75,
      },
      {
        title: 'Continuous Integration / Continuous Delivery',
        icon : 'mdi-truck-fast',
        value: 65,
      },
      {
        title: 'Git',
        icon : 'mdi-git',
        value: 67,
      },
       { divider: true },
      {
        title: 'Continuous Integration / Continuous Delivery',
        icon : 'mdi-truck-fast',
        value: 65,
      },
      {
        title: 'Git',
        icon : 'mdi-git',
        value: 67,
      },
       { divider: true },
      {
        title: 'Continuous Integration / Continuous Delivery',
        icon : 'mdi-truck-fast',
        value: 65,
      },
      {
        title: 'Git',
        icon : 'mdi-git',
        value: 67,
      },
    ],
  }),
}
</script>

<style scoped>
.title {
  border-bottom: 2px #bfbfbf solid;
  line-height: 1.5 !important;
}
.progress {
  margin-top: 0.1rem;
}
</style>
