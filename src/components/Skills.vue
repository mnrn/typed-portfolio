<template lang="pug">
  div#skills
    headline(text="Skills")
    div.main
      div.card-deck(class="d-flex justify-content-center align-items-start")
        skill-subroot(title="プログラミング言語" :subroot="langs")
        skill-subroot(title="ソフトウェアサービス" :subroot="saas")
        skill-subroot(title="OS" :subroot="os")
        skill-subroot(title="その他" :subroot="etc")
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator'
import Headline from '@/components/layouts/Headline.vue'
import SkillSubroot from '@/components/layouts/SkillSubroot.vue'

import { SkillSubtree } from '@/static/ts/skill'
import langs from '@/assets/data/ja/skill-langs.json'
import os from '@/assets/data/ja/skill-os.json'
import saas from '@/assets/data/ja/skill-saas.json'
import etc from '@/assets/data/ja/skill-etc.json'

@Component({
  components: {
    Headline,
    SkillSubroot
  }
})
export default class Skills extends Vue {
  private langs: SkillSubtree = langs
  private os: SkillSubtree = os
  private saas: SkillSubtree = saas
  private etc: SkillSubtree = etc
}
</script>

<style lang="stylus" scoped>
#skills
  padding: 50px 80px
  margin: 0 50px
  a
    color: #3344dd
</style>
