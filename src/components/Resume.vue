<script setup lang="ts">
import { ref } from 'vue'
import { useElementVisibility } from '@vueuse/core'
import { Icon } from '@iconify/vue'
import { Motion, Presence } from '@motionone/vue'
import SummarySection from './sections/SummarySection.vue'
import SkillsSection from './sections/SkillsSection.vue'
import ExperienceSection from './sections/ExperienceSection.vue'
import AchievementsSection from './sections/AchievementsSection.vue'
import EducationSection from './sections/EducationSection.vue'

const showDetails = ref({
  summary: true,
  skills: true,
  experience: true,
  achievements: true,
  education: true,
})

function toggleSection(section: keyof typeof showDetails) {
  showDetails.value[section] = !showDetails.value[section]
}
</script>

<template>
  <div class="resume-root">
    <!-- Header -->
    <Motion
      :initial="{ opacity: 0, y: -40 }"
      :animate="{ opacity: 1, y: 0 }"
      transition="{ type: 'spring', stiffness: 80 }"
      class="resume-header"
    >
      <div class="header-bg-glow"></div>
      <div class="header-content">
        <h1>Ankit Aditya</h1>
        <p class="subtitle">Director of Artificial Intelligence @ Kalkinso</p>
        <div class="contact-row">
          <span>
            <Icon icon="mdi:map-marker" /> #D/063, Meadows Vista, Morta, Ghaziabad, UP 201017
          </span>
          <span>
            <Icon icon="mdi:phone" /> <a href="tel:+918368601560">+91 83686 01560</a>
          </span>
          <span>
            <Icon icon="mdi:email" /> <a href="mailto:ankit.see@gmail.com">ankit.see@gmail.com</a>
          </span>
        </div>
        <div class="contact-row">
          <a href="https://linkedin.com/in/adykits" target="_blank" rel="noopener" aria-label="LinkedIn">
            <Icon icon="mdi:linkedin" /> linkedin.com/in/adykits
          </a>
          <a href="https://github.com/ankitaditya" target="_blank" rel="noopener" aria-label="GitHub">
            <Icon icon="mdi:github" /> github.com/ankitaditya
          </a>
        </div>
      </div>
    </Motion>

    <!-- Sections -->
    <section>
      <SectionCard
        title="Summary"
        icon="mdi:account-tie"
        :open="showDetails.summary"
        @toggle="toggleSection('summary')"
      >
        <SummarySection v-if="showDetails.summary" />
      </SectionCard>
      <SectionCard
        title="Core Skills"
        icon="mdi:star-circle"
        :open="showDetails.skills"
        @toggle="toggleSection('skills')"
      >
        <SkillsSection v-if="showDetails.skills" />
      </SectionCard>
      <SectionCard
        title="Professional Experience"
        icon="mdi:briefcase"
        :open="showDetails.experience"
        @toggle="toggleSection('experience')"
      >
        <ExperienceSection v-if="showDetails.experience" />
      </SectionCard>
      <SectionCard
        title="Achievements"
        icon="mdi:trophy"
        :open="showDetails.achievements"
        @toggle="toggleSection('achievements')"
      >
        <AchievementsSection v-if="showDetails.achievements" />
      </SectionCard>
      <SectionCard
        title="Education"
        icon="mdi:school"
        :open="showDetails.education"
        @toggle="toggleSection('education')"
      >
        <EducationSection v-if="showDetails.education" />
      </SectionCard>
    </section>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import SectionCard from './sections/SectionCard.vue'
export default defineComponent({})
</script>

<style scoped>
/* ... (same as before) ... */
.resume-root {
  max-width: 900px;
  margin: 0 auto;
  padding: 48px 16px 64px 16px;
  background: linear-gradient(120deg, #171717 60%, #262626 100%);
  border-radius: 32px;
  box-shadow: 0 8px 48px 0 #9e7fff33, 0 1.5px 0 #2f2f2f;
  color: #fff;
  font-family: 'Inter', 'sans-serif';
  position: relative;
  overflow: hidden;
}
.resume-header {
  position: relative;
  z-index: 2;
  padding-bottom: 32px;
  text-align: center;
}
.header-bg-glow {
  position: absolute;
  top: -80px;
  left: 50%;
  transform: translateX(-50%);
  width: 600px;
  height: 300px;
  background: radial-gradient(circle, #9e7fff55 0%, #17171700 80%);
  filter: blur(32px);
  z-index: 1;
  pointer-events: none;
}
.header-content h1 {
  font-size: 3rem;
  font-weight: 800;
  letter-spacing: 2px;
  margin-bottom: 0.25em;
  background: linear-gradient(90deg, #9e7fff 30%, #38bdf8 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.subtitle {
  font-size: 1.25rem;
  color: #a3a3a3;
  margin-bottom: 1em;
}
.contact-row {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5em;
  justify-content: center;
  align-items: center;
  margin-bottom: 0.5em;
  font-size: 1.05rem;
}
.contact-row a {
  color: #38bdf8;
  text-decoration: none;
  transition: color 0.2s;
}
.contact-row a:hover {
  color: #f472b6;
  text-decoration: underline;
}
@media (max-width: 600px) {
  .resume-root {
    padding: 16px 2px 32px 2px;
    border-radius: 16px;
  }
  .header-content h1 {
    font-size: 2rem;
  }
}
</style>
