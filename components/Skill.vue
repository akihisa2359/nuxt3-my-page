<template>
  <section>
    <Transition>
      <Generals-Modal
        v-if="selectedSkill"
        @close="() => (selectedSkill = null)"
      >
        <div class="skill-modal">
          {{ selectedSkillDetail }}
        </div>
      </Generals-Modal>
    </Transition>
    <div class="container">
      <h2>skill</h2>
      <div
        v-for="(categorizedSkills, category) in skills"
        :key="category"
        class="skill-section"
        :class="{ 'margin-bottom': category !== 'infra' }"
      >
        <h3 class="skill-section-title">{{ category }}</h3>
        <div class="skills">
          <div v-for="(score, skill) in categorizedSkills" class="skill">
            <div @click="selectedSkill = skill">
              {{ skill }}<Icon class="ml-s detail-icon">Add</Icon>
            </div>
            <SkillStar :score="score" />
          </div>
        </div>
      </div>

      <div class="note-wrapper">
        <div class="note">
          <div>星1: 触ったことがある</div>
          <div>星2: 基本操作ができる</div>
          <div>星3: 実務で使用できる</div>
          <div>星4: 深い理解がある</div>
          <div>星5: 専門家レベル</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { skills as skillDetails } from "/libs/constants.js";

const selectedSkill = ref(null);
const selectedSkillDetail = computed(() => skillDetails[selectedSkill.value]);

const skills = {
  frontend: {
    "HTML/CSS/JS": 4,
    "Vue/Nuxt": 4,
    "React/Next": 3,
    TypeScript: 2.5,
  },
  backend: {
    "Ruby/Rails": 4,
    "Node.js": 4,
    Python: 3.5,
  },
  infra: {
    AWS: 3.5,
    Docker: 3.5,
    Git: 4,
    CDK: 3,
  },
};
</script>

<style scoped lang="scss">
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

.skill-modal {
  width: 200px;
  height: 200px;
  padding: 24px;
  font-size: $font-s;
  letter-spacing: 2px;
  white-space: pre-wrap;
}

section {
  display: flex;
  justify-content: center;
  padding: 0 32px;
  font-size: 14px;

  .container {
    width: 100%;
    max-width: $width-sm;
    background-color: white;

    h2 {
      margin-bottom: 80px;
      letter-spacing: 12px;
      text-align: center;
      color: #96bdb9;
    }

    .skill-section {
      width: 100%;
      position: relative;
      padding: 24px 32px;
      background: rgba(180, 180, 180, 0.1);

      &.margin-bottom {
        margin-bottom: 80px;
      }

      .skill-section-title {
        position: absolute;
        top: -10px;
        left: 12px;
        padding: 0 8px;
        background: white;
        letter-spacing: 4px;
      }

      .skills {
        .skill {
          display: flex;
          justify-content: space-between;
          align-items: center;
          margin: 12px 0;
          div {
            &:first-child {
              font-size: 12px;
              color: #777;
              letter-spacing: 2px;
              padding-bottom: 4px;
              border-bottom: solid 1px #ddd;
              .detail-icon {
                font-size: 12px;
              }
              &:hover {
                cursor: pointer;
                color: black;
              }
            }
          }
        }
      }
    }

    .note-wrapper {
      padding: 12px;
      display: flex;
      justify-content: end;
      font-size: $font-xs;
      color: #333;
      letter-spacing: 2px;
    }
  }
}
</style>
