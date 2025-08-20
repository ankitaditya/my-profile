<script setup lang="ts">
import { ref } from 'vue'
const skills = [
  {
    category: 'AI Services',
    items: ['LLM', 'TTS', 'OCR', 'AI Agents'],
  },
  {
    category: 'Backend',
    items: ['Node.js', 'Python', 'TypeScript'],
  },
  {
    category: 'Frontend',
    items: ['React'],
  },
  {
    category: 'Cloud',
    items: [
      'AWS (Sagemaker, Lambda, DynamoDB, S3, Step Functions, EC2, Load Balancer)',
    ],
  },
  {
    category: 'Others',
    items: [
      'Docker',
      'GitHub Actions',
      'PostgreSQL',
      'MinIO',
      'Redis',
      'OpenSearch',
      'Keycloak SSO',
      'OAuth2',
      'API Gateway',
      'Microservices',
      'Event-driven Architecture',
    ],
  },
]
</script>
<template>
  <div class="skills-list">
    <div
      v-for="skill in skills"
      :key="skill.category"
      class="skill-category"
    >
      <h3>{{ skill.category }}</h3>
      <ul>
        <li v-for="item in skill.items" :key="item">
          <span class="dot"></span>
          {{ item }}
        </li>
      </ul>
    </div>
  </div>
</template>
<style scoped>
.skills-list {
  display: flex;
  flex-wrap: wrap;
  gap: 2em;
  justify-content: flex-start;
}
.skill-category {
  min-width: 180px;
  flex: 1 1 220px;
}
h3 {
  color: #9e7fff;
  font-size: 1.1rem;
  margin-bottom: 0.5em;
  font-weight: 700;
}
ul {
  list-style: none;
  padding: 0;
  margin: 0;
}
li {
  display: flex;
  align-items: center;
  gap: 0.5em;
  margin-bottom: 0.4em;
  color: #fff;
  font-size: 1rem;
}
.dot {
  width: 8px;
  height: 8px;
  background: linear-gradient(90deg, #9e7fff 60%, #38bdf8 100%);
  border-radius: 50%;
  display: inline-block;
}
</style>
