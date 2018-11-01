# vue-cli3-optimization

> 基于 `vue-cli@3` 做的关于 `CDN` + `Gzip` + `Prerender` + `Sass` 的优化。在基于 `vue-cli@2` 的项目 [vue-optimization](https://github.com/HaoChuan9421/vue-optimization) 里已经对这些优化方案做了详细说明。你也可以阅读我的这篇[博客](https://juejin.im/post/5b97b84ee51d450e6c7492f6)。这个仓库旨在展示最终的优化结果，细节可以通过查看 `git` 历史了解，相应的地方也有详细注释。

> 注意！！！预渲染需要下载 `Chromium` ，而由于你懂的原因，谷歌的东西在国内无法下载，所以在根目录添加了`.npmrc`文件，来使用淘宝镜像下载。[参考链接](https://github.com/cnpm/cnpmjs.org/issues/1246)。如果你的终端可以翻到国外，直接忽略这一步,你也许会喜欢[小飞机](https://juejin.im/post/5b6852b1f265da0fb0189174)

> 使用iview的同学需要注意！！！ 
> 在非 template/render 模式下（例如使用 CDN 引用时），组件名要分隔，例如 DatePicker 必须要写成 date-picker。以下组件，在非 template/render 模式下，需要加前缀 i-：

- Button: i-button
- Col: i-col
- Table: i-table
- Input: i-input
- Form: i-form
- Menu: i-menu
- Select: i-select
Option: i-option
- Progress: i-progress
- Time: i-time

> 以下组件，在所有模式下，必须加前缀 i-，除非使用 iview-loader：

- Switch: i-switch
- Circle: i-circle

> 如果已经开发大量页面，那就不要 vue 和 iview 使用cdn（两个都必须不用cdn！！！）

### 创建时的预设，详情参见`.vuerc`，[参考链接](https://cli.vuejs.org/zh/guide/creating-a-project.html#vue-create)

```json
{
  "packageManager": "npm",
  "useTaobaoRegistry": false,
  "presets": {
    "vue-optimization": {
      "useConfigFiles": true,
      "plugins": {
        "@vue/cli-plugin-babel": {},
        "@vue/cli-plugin-eslint": {
          "config": "standard",
          "lintOn": [
            "save"
          ]
        }
      },
      "router": true,
      "routerHistoryMode": true,
      "vuex": true,
      "cssPreprocessor": "sass"
    }
  }
}
```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```
