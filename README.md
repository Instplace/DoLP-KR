# DoLP-KR

[Degrees of Lewdity Plus](https://gitgud.io/Frostberg/degrees-of-lewdity-plus)(DoL+)의 한국어 번역본입니다.

원작 0.5.13.8 한국어판인 [DoL-KR](https://github.com/Instplace/DoL-KR)의 번역을 바탕으로, DoL+가 더하고 바꾼 내용을 옮겼습니다. 지금 기준으로 삼는 DoL+는 원작 0.5.13.8에 맞춘 개발 브랜치 `bec-dev`입니다.

## 받기

[릴리스](https://github.com/Instplace/DoLP-KR/releases)에서 받습니다.

- **PC**: `…-Vanilla.zip`(기본 이미지) 또는 BEEESSS, Goose, Mikili, Aoki Utage, Rotting 등 DoL+와 같은 이미지 구성의 zip. 압축을 풀고 HTML 파일을 브라우저로 엽니다.
- **안드로이드**: `….apk`. 공식 앱과 따로 설치되는 별개의 앱입니다.
- `main`은 최신판, `dev`는 시험판입니다. `dev`에 푸시될 때마다 시험판(`dev-커밋`)이 게시됩니다.

> 이 게임은 성인용입니다. 성적·폭력적인 내용을 담고 있으며 미성년자에게 적합하지 않습니다.

## 원작과 출처

- **원작**: Vrelnir의 [Degrees of Lewdity](https://vrelnir.blogspot.com/) ([소스 저장소](https://gitgud.io/Vrelnir/degrees-of-lewdity))
- **DoL+**: Frostberg와 기여자들의 [Degrees of Lewdity Plus](https://gitgud.io/Frostberg/degrees-of-lewdity-plus). 이 저장소의 첫 커밋이 그 `bec-dev` 브랜치의 파일입니다.
- **한국어 번역**: [DoL-KR](https://github.com/Instplace/DoL-KR). 그 바탕은 [아카라이브 DOL 채널](https://arca.live/b/dolgame)의 번역 참여자들이 만들고 [Ooo-eee/DoL_KrTranslation](https://github.com/Ooo-eee/DoL_KrTranslation)이 공개한 번역본입니다.

## 라이선스

원작, DoL+, 기존 번역본에 적용된 **CC BY-NC-SA 4.0**을 그대로 따릅니다. 이 저장소에서 더한 변경도 같은 조건으로 공개합니다.

- **BY (저작자표시)**: 원작과 번역본의 저작자 및 출처를 밝혀야 합니다.
- **NC (비영리)**: 영리 목적으로 이용할 수 없습니다.
- **SA (동일조건변경허락)**: 이 번역본을 고치거나 바탕으로 삼은 2차 저작물에도 같은 라이선스를 적용해야 합니다.

자세한 내용은 [`LICENSE`](LICENSE) 파일과 [라이선스 한글 요약](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.ko)을 참고하세요.

번역 기준(문체, 용어집, 인물별 말투)은 [`docs/kr-translation`](docs/kr-translation)에 있습니다.

아래로는 DoL+의 `README.md`가 이어집니다.

---

# Degrees of Lewdity Herm NPCs Mod

## Lexicon of Lewdity

Looking to contribute to Degrees of Lewdity? Read the [Lexicon of Lewdity](https://gitgud.io/Vrelnir/degrees-of-lewdity/-/wikis/home).

_Failure to do so can lead to your work being denied._

## How to build

### Changing the build version and type

1. Open `01-config\sugarcubeConfig.js`.
2. Edit the `window.StartConfig` object to the relevant config type.
    - Normal Build - `enableImages` needs to be `true` and `enableLinkNumberify` needs to be `true`.
    - Text Only Build - `enableImages` needs to be `false` and `enableLinkNumberify` needs to be `true`.
    - Android Build - `enableImages` needs to be `true` and `enableLinkNumberify` needs to be `false`.
3. `version` is optional between release versions but will be displayed on screen in several places and stored in the saves made.
4. `debug` is optional and will only effect new games.

### Compiling the html

1. On Windows: Run `compile.bat` or `compile-watch.bat`.
2. On Linux: Run `compile.sh`
3. Open `Degrees of Lewdity VERSION.html`.

### Build Android version (.apk)

See [README in devTools/apkbuilder](devTools/apkbuilder/README-windows.txt)

## Development

### Prerequisites

-   Read [Coder's-Guide](https://gitgud.io/Vrelnir/degrees-of-lewdity/-/wikis/Programming/Coder's-Guide)
-   [Node.js 16 or later](https://nodejs.org/en/).

### Optional Prerequisites

1. Install [Tweego](http://www.motoslave.net/tweego/) and remember the path where it was installed.
2. Add path to `tweego.exe` (e.g. `C:\Program Files\Twine\tweego-2.1.0-windows-x64`) to Windows `Path` environment variable.

### Initial setup

1. Install project dependencies:

    ```bash
    npm i
    ```

2. If you use Visual Studio Code:

    1. Install [Twee 3 Language Tools extension](https://marketplace.visualstudio.com/items?itemName=cyrusfirheir.twee3-language-tools)
    2. Install [ESLint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint).
    3. Install [Stylelint extension](https://marketplace.visualstudio.com/items?itemName=stylelint.vscode-stylelint)
    4. Install and optionally configure [Code Spell Checker extension](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker):
        1. Use "English - United Kingdom" and "English - United States" dictionaries
        2. Enable spellchecking for `html`, `css`, `javascript` and other relevant programming languages and dictionaries
           The extension should automatically use these settings for the project via `.cspell.json`, including the custom dictionary in `.cspell-project-words.txt`, so manual configuration should not be necessary. If running `npx cspell .` yields an absurd amount of results (including words that are in the custom dictionary), then the settings may not be automatically set or recognised, so you should set them yourself. Make sure the custom dictionary is recognised, or the extension won't be very useful!
    5. Optionally enable fixing js/css on save. In `settings.json` set:

        ```json
        // This disables built-in formatting
        "[javascript]": {
          "editor.formatOnSave": false
        },
        "[css]": {
          "editor.formatOnSave": false
        },
        // This enables running ESLint, Prettier, Stylelint formatting on file save
        "editor.codeActionsOnSave": {
          "source.fixAll.eslint": true,
          "source.fixAll.stylelint": true
        },

        ```

### Testing

To run Playwright tests, after building the game, run:

```bash
npm test
```

Tests require the compiled HTML to exist — run `./compile.sh` first if needed.

### Linting

#### JavaScript

JavaScript code linting is handled by [`ESLint`](https://eslint.org/).

ESLint is [configured](./.eslintrc.cjs) to follow some of best practices ([ESLint Recommended Rules](https://eslint.org/docs/latest/rules/), [JavaScript Standard Style](https://standardjs.com/rules.html)) with formatting handled by Prettier (`eslint --fix` formats code with Prettier). You don't need to use `Prettier` VS Code extension to format `.js` files.

To run ESLint for single file:

```bash
npx eslint "game/03-JavaScript/02-Helpers/Utils.js"
```

or for all files inside `game` directory:

```bash
npx eslint "game/**"
```

##### Resolving issues

Some issues are fixable and can be auto-fixed when you save a file (provided ESLint extension is configured to run fix on save) or by running `eslint --fix file_relative_path`

If you find a rule that doesn't make sense for the project you can disable it inside `rules` section inside `.eslintrc.cjs`:

```json
rules: {
  ...
  // SugarCube extends native objects and we follow it
  "no-extend-native": "off",
  ...
}
```

Please discuss the reasons with the team before disabling the rule. Add a comment explaining why the rule was disabled

If ESLint reports a lot of issues for particular file and you cannot fix them all at once feel free to [disable particular rule](https://eslint.org/docs/latest/user-guide/configuring/rules#disabling-rules) for the file (there is quick actions menu when code with error is hovered):

```js
/* eslint-disable camelcase -- TODO: Fix variables' names */
...
let demo_rainbow_colors = [
...
```

Add a TODO comment explaining that this will be fixed someday

##### Global variables

ESLint may report an issue like `'myVariable' is not defined`. It means ESLint cannot figure out where the variable is defined. If you really meant to make variable global add the new variable to `.eslintrc.cjs` `globals` section inside corresponding group:

```json
myVariable: "readonly"
```

If the variable is suppose to be writable set `myVariable: "writable"` instead.

### CSS

CSS linting is handled by [`Stylelint`](https://stylelint.io/).

Stylelint is [configured](./stylelint.config.cjs) to follow [common conventions](https://github.com/stylelint/stylelint-config-standard) along with [rules for properties order](https://github.com/cahamilton/stylelint-config-property-sort-order-smacss) and formatting handled by Prettier (`stylelint --fix` formats code with Prettier). You don't need to use `Prettier` VS Code extension to format `.css` files.

To run Stylelint for the file:

```bash
npx stylelint "game/02-CSS/pillsInventory.css"
```

or for all CSS file inside `game` directory:

```bash
npx stylelint "game/**/*.css"
```

#### Resolving issues

Some issues are fixable and can be auto-fixed when you save a file (provided Stylelint extension is configured to run fix on save) or by running `stylelint --fix file_relative_path`.

Sometimes all issues cannot be fixed within single "fix" run (e.g. properties order). Simply run fix command several time until all auto-fixable issues are resolved.

If you find a rule that doesn't make sense for the project you can disable it inside `rules` section inside `stylelint.config.cjs`:

```js
rules: {
  // Class and ID patterns disabled for now due to the large amounts of classes and IDs that break this rule
  "selector-class-pattern": null,
  "selector-id-pattern": null,
  ...
}
```

Please discuss the reasons with the team before disabling the rule. Add a comment explaining why the rule was disabled

### Formatting

Formatting CSS and other non-JavaScript file is handled by `Prettier`. Formatting rules are set in `.prettierrc.json`

### Pre-commit hook

On pre-commit [`lint-staged`](https://github.com/okonet/lint-staged) using [`husky`](https://typicode.github.io/husky) lints/formats `.js`, `.css` with ESLint, Stylelint and formats other supported files with Prettier.

Pre-commit hook is the last quality gate to avoid "bad" code getting into the repository. It's better to make sure you aren't committing files with issues beforehand - you can run command `npm run lint-staged` when you've staged the files to check if there are issues.

If for some reason you really want to commit the code that fails linting add `--no-verify` parameter to `commit` call

```bash
commit --no-verify
```
