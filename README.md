# Textlint <!-- omit in toc -->

- [Overview](#overview)
- [Usage](#usage)
- [Configuration](#configuration)
- [Rules](#rules)
  - [@textlint-rule/textlint-rule-no-unmatched-pair](#textlint-ruletextlint-rule-no-unmatched-pair)
  - [Textlint-rule-alive-link](#textlint-rule-alive-link)
  - [Textlint-rule-common-misspellings](#textlint-rule-common-misspellings)
  - [Textlint-rule-en-capitalization](#textlint-rule-en-capitalization)
  - [Textlint-rule-date-weekday-mismatch](#textlint-rule-date-weekday-mismatch)
  - [Textlint-rule-doubled-spaces](#textlint-rule-doubled-spaces)
  - [Textlint-rule-no-todo](#textlint-rule-no-todo)
  - [Textlint-rule-stop-words](#textlint-rule-stop-words)
  - [Textlint-rule-terminology](#textlint-rule-terminology)
  - [Textlint-rule-unexpanded-acronym](#textlint-rule-unexpanded-acronym)
  - [Textlint-rule-write-good](#textlint-rule-write-good)
- [Addons](#addons)
  - [Filters](#filters)
    - [Textlint-filter-rule-comments](#textlint-filter-rule-comments)
  - [Plugins](#plugins)
    - [Textlint-plugin-html](#textlint-plugin-html)
  - [VScode](#vscode)

## Overview

[Textlint](https://github.com/textlint/textlint) is a plug-able linting tool for text and Markdown.

Supports: `.txt`, `.md`
Required:

- Node.js 16+

Homepage: <https://github.com/textlint/textlint>
Online playground: <https://textlint.github.io/playground/>

## Usage

- To install:

```shell
npm install --save-dev textlint
```

When installed global, also install addons globally.

## Configuration

Valid configuration files are:

- `.textlintrc`
- `.textlintrc.json`
- `.textlintrc.yaml`
- `.textlintrc.js`

To create a configuration file:

```shell
npx textlint --init
```

```jsonc
{
  // .textlintrc.json
  "plugins": {},
  "filters": {},
  "rules": {}
}
```

## Rules

No defaults rules.

- [Global](https://github.com/textlint/textlint/wiki/Collection-of-textlint-rule#rules-global)
- [日本語](https://github.com/textlint/textlint/wiki/Collection-of-textlint-rule#rules-japanese)

Preset:

- [textlint-rule-preset-japanese](https://github.com/textlint-ja/textlint-rule-preset-japanese)

### @textlint-rule/textlint-rule-no-unmatched-pair

Textlint rule that check unmatched pairs like `（` and `]`.

```txt
❌ これは（秘密)です。
❌ John said "Hello World!'.
```

- <https://github.com/textlint-rule/textlint-rule-no-unmatched-pair>

### Textlint-rule-alive-link

Textlint rule to make sure every link in a document is available.

```txt
❌ https://www.goooogle.com
```

- <https://github.com/fengma1992/textlint-rule-alive-link>

### Textlint-rule-common-misspellings

Textlint rule to find common misspellings from Wikipedia: Lists of common misspellings.

```txt
❌ unsuccesful
✅ unsuccessful
```

- <https://github.com/io-monad/textlint-rule-common-misspellings>

### Textlint-rule-en-capitalization

Textlint rule that check capitalization in english text.

```txt
❌ text should be capitalized in sentences.
✅ Text should be capitalized in sentences.
```

- <https://github.com/textlint-rule/textlint-rule-en-capitalization>

### Textlint-rule-date-weekday-mismatch

Textlint rule that found mismatch between date and weekday.

```txt
❌ 2016-12-29(Friday)
✅ 2016-12-29(Thursday)
❌ 2016年12月29日(金曜日)
✅ 2016年12月29日(木曜日)
```

- <https://github.com/textlint-rule/textlint-rule-date-weekday-mismatch>

### Textlint-rule-doubled-spaces

Textlint rule for check doubled spaces in sentence.

```txt
❌ Pen  Pineapple   Apple  Pen
✅ Pen Pineapple Apple Pen
```

- <https://github.com/iwamatsu0430/textlint-rule-doubled-spaces>

### Textlint-rule-no-todo

This textlint rule check todo mark.


❌ TODO: this is TODO
❌ - [ ] TODO

- <https://github.com/textlint-rule/textlint-rule-no-todo>

### Textlint-rule-stop-words

Textlint rule to find filler words, buzzwords and clichés — 1600+ words and phrases in English.

```txt
❌ You can not use allowlist anymore.
```

- <https://github.com/sapegin/textlint-rule-stop-words>

### Textlint-rule-terminology

Textlint rule to check and fix terms, brands and technologies spelling in your tech writing in English.

```txt
❌ Javascript
✅ JavaScript
❌ front-end
✅ frontend
```

- <https://github.com/sapegin/textlint-rule-terminology>

### Textlint-rule-unexpanded-acronym

Textlint rule that found Unexpanded Acronym.

```txt
❌ I like ABC.
(What does ABC stand for ???)
```

- <https://github.com/textlint-rule/textlint-rule-unexpanded-acronym>

### Textlint-rule-write-good

textlint rule to check your English writing styles with btford/write-good.
@see <https://github.com/btford/write-good#checks>

```txt
❌ This is very good. // weasel word.
```

- <https://github.com/textlint-rule/textlint-rule-write-good>

## Addons

### Filters

#### Textlint-filter-rule-comments

Textlint rule that ignore error using comments directive.

```txt
<!-- textlint-disable -->
This is ignored           text by rule.
Disables all rules between comments
<!-- textlint-enable -->
```

- <https://github.com/textlint/textlint-filter-rule-comments>

### Plugins

#### Textlint-plugin-html

Add HTML support for textlint.

- <https://github.com/textlint/textlint-plugin-html>

### VScode

- Homepage: [taichi.vscode-textlint](https://marketplace.visualstudio.com/items?itemName=taichi.vscode-textlint)

```json
  "[markdown]": {
    "editor.defaultFormatter": "taichi.vscode-textlint"
  },
  "textlint.nodePath": "./node_modules/.bin",
  "textlint.configPath": "./.textlintrc",
  "textlint.autoFixOnSave": true,
```
