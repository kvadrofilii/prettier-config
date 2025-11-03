# prettier-config

Простая конфигурация в npm-пакете.

## Быстрый старт

Если у вас уже настроен "Prettier", просто установите и используйте:

```sh
npm install --save-dev @michael-yakovlev/prettier-config
```

Добавьте ключ `prettier` в `package.json`, чтобы использовать конфигурацию в вашем проекте:

```json
"prettier": "@michael-yakovlev/prettier-config",
```

## Детали конфигурации

```js
{
    printWidth: 120,
    tabWidth: 4,
    useTabs: false,
    semi: false,
    singleQuote: true,
    quoteProps: 'as-needed',
    trailingComma: 'all',
    bracketSpacing: true,
    objectWrap: 'preserve',
    bracketSameLine: false,
    arrowParens: 'always',
    endOfLine: 'lf',
}
```

[Ознакомьтесь с документацией "Prettier" для получения дополнительной информации о конфигурациях общего доступа](https://prettier.io/docs/sharing-configurations).

## Настройка в 3 этапа

Инструкции, если вы никогда раньше не пользовались "Prettier".

### 1. Установите Prettier

"Prettier" должен быть установлен как dev-зависимость

```sh
npm install --save-dev --save-exact prettier
```

### 2. Установите пакет и обновите файл package.json

Установите пакет с помощью `npm` (или `yarn`, или `pnpm`)

```sh
npm install --save-dev @michael-yakovlev/prettier-config
```

Добавьте ключ `prettier` в `package.json`

```diff
diff --git a/package.json b/package.json
index 2ecef3d..260838f 100644
--- a/package.json
+++ b/package.json
@@ -5,6 +5,7 @@
   "keywords": [
     "prettier"
   ],
+  "prettier": "@michael-yakovlev/prettier-config",
   "license": "MIT",
   "main": "index.js"
```

### 3. Настройка VSCode

Чтобы использовать "Prettier" в VSCode нужно установить плагин [Prettier - Code formatter](https://github.com/prettier/prettier-vscode):

В терминале VSCode выполните следующую команду:

```sh
ext install esbenp.prettier-vscode
```

Откройте файл .vscode/settings.json и добавьте настройки:

- Расширение "Prettier - Code formatter" настроено в качестве средства форматирования по умолчанию.
- Форматирование при сохранении включено.

```json
{
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true
}
```

## Расширение конфигурации

Чтобы расширить конфигурацию и перезаписать некоторые свойства из конфигурации, импортируйте в файл `.prettierrc.mjs` конфиг и экспортируйте изменения, например:

```js
// .prettierrc.mjs
import prettierConfig from '@michael-yakovlev/prettier-config'

/**
 * @type {import("prettier").Config}
 */
const config = {
    ...prettierConfig,
    tabWidth: 2,
}

export default config
```
