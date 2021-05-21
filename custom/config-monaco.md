# Configure Monaco

<Environment type="client" />

> By default, Monaco only is enabled only on dev mode. To make it work on SPA build, add `monaco: true` to your frontmatter configs.

Crea `./setup/monaco.ts` con el siguiente contenido:

```ts
import { defineMonacoSetup } from '@slidev/types'

export default defineMonacoSetup(async (monaco) => {
  // use `monaco` to configure
})
```

Learn more about [configuring Monaco](https://github.com/Microsoft/monaco-editor).

## Usage

To use Monaco in your slides, simply append `{monaco}` to your code snippets:

~~~js
//```js
const count = ref(1)
const plusOne = computed(() => count.value + 1)

console.log(plusOne.value) // 2

plusOne.value++ // error
//```
~~~

To

~~~js
//```js {monaco}
const count = ref(1)
const plusOne = computed(() => count.value + 1)

console.log(plusOne.value) // 2

plusOne.value++ // error
//```
~~~

## Exporting

By default, Monaco will ONLY work on `dev` mode. If you would also like to have it available in the exported SPA, you can configure it in your frontmatter:

```yaml
---
monaco: true # default "dev"
---
```

## Types Auto Installing

When you use TypeScript with Monaco, types for dependencies will be installed to the client-side automatically.

~~~ts
//```ts {monaco}
import { ref } from 'vue'
import { useMouse } from '@vueuse/core'

const counter = ref(0)
//```
~~~

In the example above, just make sure `vue` and `@vueuse/core` are installed locally as dependencies / devDependencies, Slidev will handle the rest and your editor will just work!
