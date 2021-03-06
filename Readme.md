# V-Emoji-Picker
This simple package using Emojis Natives

[![npm](https://img.shields.io/npm/v/v-emoji-picker.svg?style=flat-square)](https://www.npmjs.com/package/v-emoji-picker)
[![bundlephobia](https://img.shields.io/bundlephobia/minzip/v-emoji-picker.svg?style=flat-square)](https://bundlephobia.com/result?p=v-emoji-picker@latest)
[![npm](https://img.shields.io/npm/dm/v-emoji-picker.svg?style=flat-square)](https://www.npmjs.com/package/v-emoji-picker)
[![vue2](https://img.shields.io/badge/vue-2.x-brightgreen.svg?style=flat-square)](https://vuejs.org/)
[![CodeFactor](https://www.codefactor.io/repository/github/joaoeudes7/v-emoji-picker/badge?style=flat-square)](https://www.codefactor.io/repository/github/joaoeudes7/v-emoji-picker)
![example: Android](.demo.png)

---
## Contents
- [Installation](#installation)
- [Usage](#usage)
- [Props](#props)
- [Events](#events)
- [Updates v2](#updates-version-2)
- [Migrate v2](#migrate-to-version-2)
- [Using SVG](#using-SVG)
- [Structure emoji](#structure-emoji)
----

# Installation
```bash
yarn add v-emoji-picker
```
# Usage
```vue
<template>
  <div id="app">
    <VEmojiPicker @select="selectEmoji" />
  </div>
</template>

<script>
import VEmojiPicker from 'v-emoji-picker';

export default {
  name: 'Demo',
  components: {
    VEmojiPicker
  },
  data: () => ({}),
  methods: {
    selectEmoji(emoji) {
      console.log(emoji)
    }
  }
}
</script>
```

or Global

```js
import Vue from "vue";
import App from "./App.vue";

import { VEmojiPicker } from 'v-emoji-picker';

Vue.config.productionTip = false;
Vue.use(VEmojiPicker);

new Vue({
  render: h => h(App)
}).$mount("#app");
```

## Props
```ts
{
  @Prop({ default: () => [] as IEmoji[] }) customEmojis!: IEmoji[];
  @Prop({ default: () => [] as ICategory[] }) customCategories!: ICategory[];
  @Prop({ default: 5 }) emojisByRow!: number;
  @Prop({ default: false }) continuousList!: boolean;
  @Prop({ default: true }) showSearch!: boolean;
  @Prop({ default: true }) showCategories!: boolean;
  @Prop({ default: "Pesquisar..." }) labelSearch!: string;
  @Prop({ default: "Peoples" }) initalCategory!: string;
  @Prop({ default: () => [] as string[] }) exceptCategories!: string[];
}
```

## Events
```js
{
  select: 'Emit event on Selected Emoji',
  changeCategory: 'Emit event on Change Category'
}
```

# Using custom Emojis
Array of items with `Interface IEmoji`

```js
interface IEmoji {
  data: string;
  category: string;
  aliases: string[];
}
```

set in Prop `customEmojis`

# Using custom Categories
Array of items with `Interface ICategory`

```js
interface ICategory {
  name: string;
  icon: string;
}
```

set in Prop `customCategories`

# Using SVG
Doc coming soon...

# Updates version 2
- Prop `customEmojis`
- Prop `customCategories`
- Prop `exceptCategories`
- Folder /data removed
- Interface Emoji updated
- Support to Emojis SVG/Img/Natives (text)

# Migrate to version 2
This was a one-time change to keep it clear and dynamic.

- Prop `pack` removed (async auto import default emojis natives - text)
- Prop `showCategory` changed to `showCategories`
- Event content `event.emoji` changed to `emoji.data`

# Structure Emoji
![](.emoji.png)

## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fjoaoeudes7%2FV-Emoji-Picker.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fjoaoeudes7%2FV-Emoji-Picker?ref=badge_large)
