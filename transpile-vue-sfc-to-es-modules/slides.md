---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
---

# Transpile Vue SFC To ES Modules

将 Vue SFC 转化为 ES Modules

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 p-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Getting Started <carbon:arrow-right class="inline"/>
  </span>
</div>

<a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
  class="abs-br m-6 text-xl icon-btn opacity-50 !border-none !hover:text-white">
  <carbon-logo-github />
</a>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---

# What is SFC?

[SFC](https://v3.vuejs.org/guide/single-file-component.html#introduction) is Single-File Component in Vue Project, It describe a Vue component.
  
- 📝 **template** - focus on the content with Markdown, and then style them later
- 🎨 **script** - theme can be shared and used with npm packages
- 🎨 **style** - code highlighting, live coding with autocompletion

<br>
<br>

Read more about

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/guide/syntax#embedded-styles
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
layout: image-left
image: https://source.unsplash.com/collection/94734566/1920x1080
---
# 未来前端工程构建

### 下一代构建工具

2021 年的今天，已经涌现出了一批新的，可以称之为下一代的前端构建工具，例如 `esbuild`、`snowpack`、`vite`、`wmr` 等等。

可以看看这篇文章[《Comparing the New Generation of Build Tools》](https://css-tricks.com/comparing-the-new-generation-of-build-tools/)，从**工具配置**、**开发服务**、**生产构建**、**构建SSR**等方面分析比较了前端下一代的构建工具。

---
layout: image-left
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# 浏览器原生构建

### 在浏览器中使用 JavaScript 模块

现代浏览器已经原生支持加载 `ES Modules` ，需要将 `type="module"` 放到 `<script>` 标签中，来声明这个脚本是一个模块，例如：

```html
<script type="module">
  // include script here
</script>
```

这样就可以在脚本中使用 `import` 、`export` 语句了

![caniuse](images/caniuse.png)

---
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# 浏览器原生构建

### 在 Node.js 中处理依赖关系

现代前端工程开发环境中，会根据 `package.json` 来描述模块之间的依赖关系，安装模块后，所有模块会放在`node_modules` 文件夹下。例如 package.json 中描述依赖了lodash：

```json {5}
{
  "name": "test",
  "version": "0.0.1",
  "dependencies": {
    "lodash": "^4.17.21"
  }
}
```

---
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# 浏览器原生构建

### 在浏览器中处理依赖关系

类似的，在浏览器中处理模块之间的依赖关系，目前有一个新的提案 `import-maps`，通过声明 `<script>` 标签的属性 `type` 为 `importmap`，来定义模块的名称和模块地址之间的映射关系，例如：

```json {4}
<script type="importmap">
{
  "imports": {
    "lodash": "https://cdn.jsdelivr.net/npm/lodash@4.17.21/lodash.min.js"
  }
}
</script>
```

---

# Components

<div grid="~ cols-2 gap-4">
<div>

You can use Vue components directly inside your slides.

We have provided a few built-in components like `<Tweet/>` and `<Youtube/>` that you can use directly use. And add your custom components are also super easy.

```md
<Counter :count="10" />
```

<!-- ./components/Counter.vue -->
<Counter :count="10" m="t-4" />

Check out [the guides](https://sli.dev/custom/#components) for more.

</div>
<div>

```html
<Tweet id="1390115482657726468" />
```

<Tweet id="1390115482657726468" scale="0.65" />

</div>
</div>

---

# LaTeX

LaTeX is supported out-of-box powered by [KaTeX](https://katex.org/).

<br>

Inline $\sqrt{3x-1}+(1+x)^2$

Block
$$
\begin{array}{c}

\nabla \times \vec{\mathbf{B}} -\, \frac1c\, \frac{\partial\vec{\mathbf{E}}}{\partial t} &
= \frac{4\pi}{c}\vec{\mathbf{j}}    \nabla \cdot \vec{\mathbf{E}} & = 4 \pi \rho \\

\nabla \times \vec{\mathbf{E}}\, +\, \frac1c\, \frac{\partial\vec{\mathbf{B}}}{\partial t} & = \vec{\mathbf{0}} \\

\nabla \cdot \vec{\mathbf{B}} & = 0

\end{array}
$$

<br>

[Learn more](https://sli.dev/guide/syntax#latex)

---
class: px-20
---

# Themes

Slidev comes with powerful theming support. Themes are able to provide styles, layouts, components, or even configurations for tools. Switching between themes by just **one edit** in your frontmatter:

<div grid="~ cols-2 gap-2" m="-t-2">

```yaml
---
theme: default
---
```

```yaml
---
theme: seriph
---
```

<img border="rounded" src="https://sli.dev/themes/default.png">

<img border="rounded" src="https://sli.dev/themes/seriph.png">

</div>

Read more about [How to use a theme](https://sli.dev/themes/use.html) and
check out the [Awesome Themes Gallery](https://sli.dev/themes/gallery.html).


---
layout: center
class: text-center
---

# Learn More

[Documentations](https://sli.dev) / [GitHub Repo](https://github.com/slidevjs/slidev)
