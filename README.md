# vue-instagram

[![npm](https://img.shields.io/npm/v/vue-instagram.svg)](https://www.npmjs.com/package/vue-instagram)
[![npm](https://img.shields.io/npm/dt/vue-instagram.svg)](https://www.npmjs.com/package/vue-instagram)
[![npm](https://img.shields.io/npm/dm/vue-instagram.svg)](https://www.npmjs.com/package/vue-instagram)
[![npm](https://img.shields.io/npm/l/vue-instagram.svg)](http://opensource.org/licenses/MIT)

Instagram's feed fetcher component based on [Vue](https://vuejs.org/).

**Works with Vue 2.***

## Demo

[My Instagram's feed](https://kevinongko.github.io/vue-instagram/)

## Installation

### Install via CDN
```html
<script src="https://unpkg.com/vue"></script>
<script src="https://unpkg.com/vue-instagram"></script>

<script>
  Vue.use(VueInstagram.default)
</script>
```

### Install via NPM
```sh
$ npm install vue-instagram --save
```

#### Register as Component
```js
import Vue from 'vue'
import VueInstagram from 'vue-instagram'

export default {
  name: 'App',

  components: {
    VueInstagram
  }
}
```

#### Register as Plugin
```js
import Vue from 'vue'
import VueInstagram from 'vue-instagram'

Vue.use(VueInstagram)
```

## Usage

Style your feeds using [scoped slot](https://vuejs.org/v2/guide/components.html#Scoped-Slots)

```vue
<template>
  <vue-instagram token="accessTokenHere" username="kevinongko" :count="5" :tags="['hashtag1', 'hashtag2']">
    <template slot="feeds" slot-scope="props">
      <li class="fancy-list"> {{ props.feed.link }} </li>
    </template>
    <template slot="error" slot-scope="props">
      <div class="fancy-alert"> {{ props.error.error_message }} </div>
    </template>
  </vue-instagram>
</template>

<script>
import VueInstagram from 'vue-instagram'

export default {
  name: 'App',

  components: {
    VueInstagram
  }
}
</script>

```

## Props
|Props|Description|Type|Required|
|-----|-----------|----|--------|
|token|Instagram's access token|String|true|
|username|Instagram's username (token's owner)|String|true|
|count|Numbers of feed to fetch|Number|true
|tags|Filter profile's feed by hastag|Array|false

## License

Vue-Instagram is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)
