# nuxt-typescript-error

## A fresh created Nuxt App shows TypeScript errors when building

### Steps to reproduce

* Initialize a Nuxt App with TypeScript as programming language
* Add a component that uses props with PropType or PropOptions
* Use the props in your component, e.g. by adding a computed property or by accessing props in the mounted hook
* Run the `build` command

### Expected result

* Build compiles successfully without any errors

### Actual result

* TypeScript errors

```
Hash: 6251f8fae46627c67cb3
Version: webpack 4.46.0
Time: 9301ms
Built at: 08/05/2021 4:51:38 PM
     Asset       Size  Chunks               Chunk Names
03bd1aa.js    213 KiB       1  [immutable]  commons/app
20232b0.js  559 bytes       3  [immutable]  components/test
6bbd920.js   6.86 KiB    5, 4  [immutable]  pages/index
9b32ed3.js   6.58 KiB       4  [immutable]  components/tutorial
  LICENSES  407 bytes                       
adeb2d1.js   2.33 KiB       6  [immutable]  runtime
d5117bf.js   1.85 KiB       2  [immutable]  components/nuxt-logo
e23bc49.js   57.6 KiB       0  [immutable]  app
Entrypoint app = adeb2d1.js 03bd1aa.js e23bc49.js

ERROR in components/Test.vue:25:22
TS2339: Property 'foo' does not exist on type 'ComponentOptions<Vue, DefaultData<Vue>, DefaultMethods<Vue>, DefaultComputed, PropsDefinition<DefaultProps>, DefaultProps>'.
    23 |   },
    24 |   mounted () {
  > 25 |     console.log(this.foo)
       |                      ^^^
    26 |     console.log(this.bar)
    27 |     console.log(this.$axios)
    28 |     console.log(this.$el)

ERROR in components/Test.vue:26:22
TS2339: Property 'bar' does not exist on type 'ComponentOptions<Vue, DefaultData<Vue>, DefaultMethods<Vue>, DefaultComputed, PropsDefinition<DefaultProps>, DefaultProps>'.
    24 |   mounted () {
    25 |     console.log(this.foo)
  > 26 |     console.log(this.bar)
       |                      ^^^
    27 |     console.log(this.$axios)
    28 |     console.log(this.$el)
    29 |   }

ERROR in components/Test.vue:27:22
TS2339: Property '$axios' does not exist on type 'ComponentOptions<Vue, DefaultData<Vue>, DefaultMethods<Vue>, DefaultComputed, PropsDefinition<DefaultProps>, DefaultProps>'.
    25 |     console.log(this.foo)
    26 |     console.log(this.bar)
  > 27 |     console.log(this.$axios)
       |                      ^^^^^^
    28 |     console.log(this.$el)
    29 |   }
    30 | })

ERROR in components/Test.vue:28:22
TS2339: Property '$el' does not exist on type 'ComponentOptions<Vue, DefaultData<Vue>, DefaultMethods<Vue>, DefaultComputed, PropsDefinition<DefaultProps>, DefaultProps>'.
    26 |     console.log(this.bar)
    27 |     console.log(this.$axios)
  > 28 |     console.log(this.$el)
       |                      ^^^
    29 |   }
    30 | })
    31 | </script>

 FATAL  Nuxt build error                                                                                                                                                                        16:51:38

  at WebpackBundler.webpackCompile (node_modules/@nuxt/webpack/dist/webpack.js:2127:21)
  at runMicrotasks (<anonymous>)
  at processTicksAndRejections (internal/process/task_queues.js:95:5)
  at async WebpackBundler.build (node_modules/@nuxt/webpack/dist/webpack.js:2076:5)
  at async Builder.build (node_modules/@nuxt/builder/dist/builder.js:327:5)
  at async Object.run (node_modules/@nuxt/cli/dist/cli-build.js:110:7)
  at async NuxtCommand.run (node_modules/@nuxt/cli/dist/cli-index.js:413:7)


   ╭─────────────────────────────╮
   │                             │
   │   ✖ Nuxt Fatal Error        │
   │                             │
   │   Error: Nuxt build error   │
   │                             │
   ╰─────────────────────────────╯
```
