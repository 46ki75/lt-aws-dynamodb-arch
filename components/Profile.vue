<template>
  <div :class="$style.wrapper">
    <div :class="$style.header">
      <div :class="$style.name">
        <ruby>
          山下
          <rt>Yamashita</rt>
        </ruby>
        <ruby>
          生真
          <rt>Ikuma</rt>
        </ruby>
      </div>

      <div>
        <img :class="$style.portrait" src="../images/portrait.png" alt="" />
        <div :class="$style.github">
          <Icon icon="mdi:github" height="1.5rem" />
          <a href="https://github.com/46ki75">46ki75</a>
        </div>
      </div>
    </div>
    <p>クラウドインフラエンジニア / AWS 上での Red Hat 系のサーバー構築など</p>
    <p>学生時代からの趣味として OSS 開発なども行う</p>
  </div>
</template>

<script setup lang="ts">
import { Icon } from "@iconify/vue";

export interface ProfileProps {}

withDefaults(defineProps<ProfileProps>(), {});
</script>

<style module lang="scss">
.wrapper {
  margin-top: 4rem;
}

.header {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-between;
}

.name {
  font-size: 3.5rem;
  white-space: nowrap;

  rt {
    padding-bottom: 0.5rem;
    opacity: 0.75;
  }
}

.portrait {
  max-width: 128px;
  max-height: 128px;
  border-radius: 50%;
  margin-bottom: 1rem;
}

.github {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 0.5rem;
}
</style>
