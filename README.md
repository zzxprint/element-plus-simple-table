## How to run
- npm install
- npm run dev

## How to use it in my project
- copy the `SimpleTable` component
- install the `@vitejs/plugin-vue-jsx`
- and don't forget to import `Icons` in main.ts

```ts
import { createApp } from 'vue'
import * as Icons from "@element-plus/icons-vue"
import App from './App.vue'

const app = createApp(App)

Object.keys(Icons).forEach(key => {
  app.component(key, Icons[key as keyof typeof Icons])
})
app.mount('#app')
```

## Extend the component by yourself
you can extend whatever you need in `SimpleTable` like add a `el-pagination`