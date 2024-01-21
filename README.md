# LINT SETUP

A brief description of what this project does and who it's for

### `git clone https://github.com/learnwithsumit/think-in-a-react-way.git`

# Editor Setup

### You can use any editor but as I personally prefer VS Code. I will give some instructions about how I prefer VS code to be setup for React applications.

## Plugins

You need to install the below plugins:

- ESLint by Dirk Baeumer
- Prettier - Code formatter by Prettier
- Dracula Official Theme (optional)

## Settings

Follow the below settings for VS Code -

- Create a new folder called ".vscode" inside the project root folder
- Create a new file called "settings.json" inside that folder.
- Paste the below json in the newly created settings.json file and save the file.

#### Configuration

```json
{
  // Theme
  "workbench.colorTheme": "Dracula",

  // config related to code formatting
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "[javascript]": {
    "editor.formatOnSave": false,
    "editor.defaultFormatter": null
  },
  "[javascriptreact]": {
    "editor.formatOnSave": false,
    "editor.defaultFormatter": null
  },
  "javascript.validate.enable": false, //disable all built-in syntax checking
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.fixAll.tslint": true,
    "source.organizeImports": true
  },
  "eslint.alwaysShowStatus": true,
  // emmet
  "emmet.triggerExpansionOnTab": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  }
}
```

## Set Line Breaks

Make sure in your VS Code Editor, "LF" is selected as line feed instead of CRLF (Carriage return and line feed). To do that, just click LF/CRLF in bottom right corner of editor, click it and change it to "LF". If you dont do that, you will get errors in my setup.

## Linting Setup

Install Dev Dependencies

```bash
yarn add -D prettier
yarn add -D babel-eslint
npx install-peerdeps --dev eslint-config-airbnb
yarn add -D eslint-config-prettier eslint-plugin-prettier
```

#### or You can also add a new script in the scripts section like below to install everything with a single command:

```json
scripts: {
    "lint": "yarn add -D prettier && yarn add -D babel-eslint && npx install-peerdeps --dev eslint-config-airbnb && yarn add -D eslint-config-prettier eslint-plugin-prettier"
}
```

after added script run this command bellow:

### `yarn lint #or npm run lint`

## Create Linting Configuration file manually

### Create a .eslintrc file in the project root and enter the below contents:

```json
{
  "extends": [
    "airbnb",
    "airbnb/hooks",
    "eslint:recommended",
    "prettier",
    "plugin:jsx-a11y/recommended"
  ],
  "parser": "babel-eslint",
  "parserOptions": {
    "ecmaVersion": 8
  },
  "env": {
    "browser": true,
    "node": true,
    "es6": true,
    "jest": true
  },
  "rules": {
    "react/react-in-jsx-scope": 0,
    "react-hooks/rules-of-hooks": "error",
    "no-console": 0,
    "react/state-in-constructor": 0,
    "indent": 0,
    "linebreak-style": 0,
    "react/prop-types": 0,
    "jsx-a11y/click-events-have-key-events": 0,
    "react/jsx-filename-extension": [
      1,
      {
        "extensions": [".js", ".jsx"]
      }
    ],
    "prettier/prettier": [
      "error",
      {
        "trailingComma": "es5",
        "singleQuote": true,
        "printWidth": 100,
        "tabWidth": 4,
        "semi": true,
        "endOfLine": "auto"
      }
    ]
  },
  "plugins": ["prettier", "react", "react-hooks"]
}


# Demo

step 1. 
npm install eslint eslint-plugin-react eslint-plugin-react-hooks --save-dev

.eslintrc.json file
---------------
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "extends": [
        "eslint:recommended",
        "plugin:react/recommended",
        "plugin:react-hooks/recommended"
    ],
    "parserOptions": {
        "ecmaVersion": 12,
        "sourceType": "module",
        "ecmaFeatures": {
            "jsx": true
        }
    },
    "plugins": ["react", "react-hooks"],
    "rules": {
        "react/no-unused-prop-types": "error",
        "react/react-in-jsx-scope": "off",
        "react/prop-types": "off",
        "sort-imports": [
            "error",
            {
                "ignoreCase": false,
                "ignoreDeclarationSort": true,
                "ignoreMemberSort": false,
                "memberSyntaxSortOrder": ["none", "all", "multiple", "single"],
                "allowSeparatedGroups": false
            }
        ]
    }
}




folder .vscode (settings-->workspace-->open settings.json file top-right button)
settings.json
---------------

{
    // config related to code formatting
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true,
    "[javascript]": {
        "editor.formatOnSave": true,
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[javascriptreact]": {
        "editor.formatOnSave": true,
        "editor.defaultFormatter": null
    },
    //disable all built-in syntax checking
    "javascript.validate.enable": false,
    // "prettier.trailingComma": "none",
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": "explicit",
        "source.fixAll.tslint": "explicit",
        "source.organizeImports": "explicit"
    },
    // emmet
    "emmet.triggerExpansionOnTab": true,
    "emmet.includeLanguages": {
        "javascript": "javascriptreact"
    },
    "prettier.tabWidth": 2,
    "prettier.printWidth": 120,
    "prettier.singleQuote": true
}

```
