<template>
  <section>
    <div class="container">
      <h2>skill</h2>
      <div class="skill-section">
        <h3 class="skill-section-title">frontend</h3>
        <div class="skills">
          <div class="skill">
            <div>HTML/CSS/JS<Icon class="ml-s detail-icon">Add</Icon></div>
            <SkillStar score="4" />
          </div>
          <div class="skill">
            <div>Vue/Nuxt<Icon class="ml-s detail-icon">Add</Icon></div>
            <SkillStar score="4" />
          </div>
          <div class="skill">
            <div>React/Next<Icon class="ml-s detail-icon">Add</Icon></div>
            <SkillStar score="3" />
          </div>
          <div class="skill">
            <div>TypeScript<Icon class="ml-s detail-icon">Add</Icon></div>
            <SkillStar score="2.5" />
          </div>
        </div>
      </div>

      <div class="skill-section">
        <h3 class="skill-section-title">backend</h3>
        <div class="skills">
          <div class="skill">
            <div>Ruby/Rails<Icon class="ml-s detail-icon">Add</Icon></div>
            <SkillStar score="3" />
          </div>
          <div class="skill">
            <div>Node.js<Icon class="ml-s detail-icon">Add</Icon></div>
            <SkillStar score="3" />
          </div>
          <div class="skill">
            <div>Python<Icon class="ml-s detail-icon">Add</Icon></div>
            <SkillStar score="3" />
          </div>
        </div>
      </div>

      <div class="skill-section">
        <h3 class="skill-section-title">infra</h3>
        <div class="skills">
          <div class="skill">
            <div>AWS<Icon class="ml-s detail-icon">Add</Icon></div>
            <SkillStar score="3" />
          </div>
          <div class="skill">
            <div>Docker<Icon class="ml-s detail-icon">Add</Icon></div>
            <SkillStar score="3" />
          </div>
          <div class="skill">
            <div>Git<Icon class="ml-s detail-icon">Add</Icon></div>
            <SkillStar score="3" />
          </div>
          <div class="skill">
            <div>CDK<Icon class="ml-s detail-icon">Add</Icon></div>
            <SkillStar score="3" />
          </div>
        </div>
      </div>
    </div>

    <div class="circle" />

    <div style="height: 800px" />
  </section>
  <SkillStar :score="2.5" />
</template>

<script setup>
import SkillCircle from "./SkillCircle.vue";
</script>

<style scoped lang="scss">
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

      &:not(:last-child) {
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
  }
}
</style>
