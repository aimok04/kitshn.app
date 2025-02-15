---
description: kitshn is available on Github, F-Droid and Google Play
---

<script setup>
import badge from "./components/badge.vue"
import { ref, onMounted } from 'vue'

const gh = ref([])

onMounted(async () => {
  const ghres = await fetch('https://api.github.com/repos/aimok04/kitshn/releases')
  gh.value = await ghres.json()
  
  if(gh.value[0]?.name === "nightly") gh.value.shift()
})
</script>

# Download <Badge style="margin-top: 14px" type="tip" :text="gh?.[0]?.name || '...'" />

::: tip
F-Droid releases are delayed by up to one week. Use **IzzyOnDroid**, **Obtainium** or **Google Play** to receive updates faster.
:::

## Built and signed by myself
<div style="display: flex; flex-direction: row; flex-wrap: wrap">
    <badge src="izzyondroid" label="IzzyOnDroid" link="https://android.izzysoft.de/repo/apk/de.kitshn.android" />
    <badge src="obtainium" label="Obtainium" link="obtainium://add/github.com/aimok04/kitshn" />
    <badge src="github" label="GitHub" link="https://github.com/aimok04/kitshn/releases" />
</div>

### Verified open source
Signed by myself, verified open source with [reproducible builds](https://f-droid.org/docs/Reproducible_Builds/).

<badge src="fdroid" label="F-Droid" link="https://f-droid.org/de/packages/de.kitshn.android/" />

## iOS and iPadOS
<div style="display: flex; flex-direction: row; flex-wrap: wrap">
  <badge src="apple" label="App Store" link="https://apps.apple.com/us/app/kitshn-for-tandoor/id6740168361" />
</div>

## Signed by Google
::: danger
Reject Google, return to privacy.
:::

<badge src="google_play" label="Google Play" link="https://play.google.com/store/apps/details?id=de.kitshn.android" />