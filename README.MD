# VS Code Specific Configs

## Recommended Extensions
- Docker [`peterjausovec.vscode-docker`]
- DotENV [`mikestead.dotenv`]
- EditorConfig for VSS Code [`editorconfig.editorconfig`]
- ESLint [`dbaeumer.vscode-eslint`]
- Markdown Preview Enhanced [`shd101wyy.markdown-preview-enhanced`]
- Prettier - Code formatter [`esbenp.prettier-vscode`]

## Editorconfig
- File: `.editorconfig`
- Configuration:
```
# http://editorconfig.org
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

[*.pug]
indent_style = tab

[*.md]
trim_trailing_whitespace = false

[*.php]
indent_style = space
indent_size = 4
```

## JS Config
- File: `jsconfig.json`
- Configuration: 
```
{
  "compilerOptions": {
    // "target": "es5",
    // "allowSyntheticDefaultImports": false,
    "baseUrl": "./resources/assets/js",

  },
  "exclude": [
      "node_modules",
      "public",
  ],
}
```

### Description
baseUrl provides a path for the IDE to resolve imports thereby providing a single click path to open the linked/imported file


## Workspace Settings
- File: .vscode/settings.json
- Configuration: 
```
{
    // "eslint.run": "onSave",
    // Set the default
    "editor.formatOnSave": false,
    // Enable per-language
    "[javascript]": {
        "editor.formatOnSave": true
    },
    
    "javascript.validate.enable": false,
    "editor.minimap.maxColumn": 80,
    "eslint.autoFixOnSave": false,
    "eslint.packageManager": "yarn",
    "eslint.options": { "configFile": "./.eslintrc" }
}
```
### Description
With the extension 'Prettier' [esbenp.prettier-vscode] intalled and you can leverage automatic file formatting on Save

## Extension - Prettier
- Extension: `esbenp.prettier-vscode`
- Configuration File: `.prettierrc`
- Configuration: 
```
{
  "printWidth": 80,
  "parser": "flow",
  "tabWidth": 2,
  "semi": true,
  "singleQuote": true,
  "trailingComma": "all",
  "jsxBracketSameLine": true,
  "insertPragma": false,
  "requirePragma": false
}
```
### Description
Note: This config will work along with your `editorconfig.js` for automatically format your code.

## Extension - ESLint
- Extension: `dbaeumer.vscode-eslint`
- Configuration File: `.eslintrc`
- Configuration:
```
{
  "extends": [
    "airbnb",
    "plugin:prettier/recommended"
  ],
  "parser": "babel-eslint",
  "plugins": [
    "flowtype",
    "import",
		"cypress"
  ],
  "rules": {
    "react/no-unescaped-entities": [0],
    "react/jsx-closing-bracket-location": [0],
    "no-confusing-arrow": [0],
    "function-paren-newline": 0,
    "max-len": 0,
    "linebreak-style": [0],
    "react/prop-types": [0],
    "arrow-parens": [0],
    "no-mixed-operators": [0],
    "react/no-array-index-key": [0],
    "import/extensions": [0],
    "react/jsx-filename-extension": [1, { "extensions": [".js", ".jsx"]}],
    "react/prefer-es6-class": [2, "always"],
    "react/default-props-match-prop-types": [0],
    "react/jsx-no-bind": [0],
    "jsx-a11y/label-has-for": [0],
    "jsx-a11y/anchor-is-valid": [0],
    "no-floating-decimal": 0,
    "no-multiple-empty-lines": 0,
    "no-use-before-define": 0,
    "react/no-unused-prop-types": [2, { "skipShapeProps": true }],
    "func-names": 0,
    "camelcase": 0,
    "eqeqeq": 1,
    "react/forbid-prop-types": [1, { "forbid": ["any"]}],
    "react/jsx-indent": 0,
    "import/no-named-as-default" : 0,
    "import/prefer-default-export": 0,
    "flowtype/require-parameter-type": 0,
    "flowtype/space-after-type-colon": [ 2, "always", { "allowLineBreak": true } ],
    "flowtype/space-before-type-colon": [
      1,
      "never"
    ],
    "flowtype/require-return-type": [0, "never", {
      "excludeMatching": ["componentWillMount", "componentWillUnmount"]
    }]
  },
  "parserOptions": {
    "ecmaVersion": 7,
    "ecmaFeatures": {
      "experimentalObjectRestSpread": true
    }
  },
  "settings": {
    "flowtype": {
      "onlyFilesWithFlowAnnotation": true
    },
    "import/resolver": {
      "webpack": {
          "config": "webpack.config.base"
      }
  }
  },
  "globals": {
    "$": true,
    "window": true,
    "document": true,
    "FormData": true,
    "location": true,
	  "Cypress": true,
		"cy": true,
		"it": true,
		"xhr": true,
		"describe": true,
		"beforeEach": true,
		"expect": true,
		"context": true,
		"localStorage": true,
    "before": true,
    "React$Element": true,
    "HTMLElement": true,
    "Event": true,
    "HTMLInputElement": true,
    "$R": true,
    "React$Component": true
  }
}
```

## Global Git Config
- File: ~/.gitconfig
- Configuration:
```
[core]
	excludesfile = /Users/seb/.gitignore_global
	editor = code --wait
...
```

### Description
`editor` defines the app to use when marking commits for an interactive rebase, in this case 'code' references VS Code app.