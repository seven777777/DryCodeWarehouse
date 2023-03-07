# vscode settings

项目内的配置文件优先级会大于全局配置

.vscode\settings.json 文件需要加入到版本库，但.vscode 文件夹下的其它文件需要忽略，因此修改.gitignore 文件：

```
步骤一：
删除原来的.vscode
步骤二：
在文件末尾新增
.vscode/\*
!.vscode/settings.json
.vscode
```

```json
//.vscode/settings.json
{
    // editor
    "editor.formatOnSave": true,
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
    "editor.tabSize": 4,
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    //默认采用格式化工具
    "[html]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[json]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[jsonc]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[vue]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[javascript]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[javascriptreact]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[typescript]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[typescriptreact]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },

    //eslint
    "eslint.format.enable": false,
    "eslint.validate": [
        "javascript",
        "javascriptreact",
        "vue",
        "typescript",
        "typescriptreact"
    ],

    //prettier 配置
    "prettier.printWidth": 150,
    "prettier.semi": false,
    "prettier.tabWidth": 4,
    "prettier.singleQuote": true,
    "prettier.trailingComma": "none",
    "prettier.endOfLine": "auto",
    "arrowParens": "avoid",

    //vetur
    "vetur.format.defaultFormatter.js": "prettier",
    "vetur.format.defaultFormatter.html": "prettyhtml",
    "vetur.format.defaultFormatterOptions": {
        "prettier": {},
        "prettyhtml": {
            // "singleQuote": true
        }
    },
    "vetur.validation.template": false
}
```
