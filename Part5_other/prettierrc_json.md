# .prettierrc.json

注释版：

```json
//.prettierrc.json

{
    "useTabs": false, // 使用 tabs 替代空格
    "tabWidth": 4, //缩进字节
    "printWidth": 120, //屏幕显示宽度（一行做多容纳字节数，超过自动换行）
    "semi": true, // 行尾 分号
    "singleQuote": true, // 使用单引号, 默认false
    "arrowParens": "avoid", // 箭头函数一个参数是否使用括号包裹参数 always/avoid
    "bracketSpacing": true, //对象，数组括号与文字之间加空格 { foo: bar }
    "trailingComma": "all", //对象或数组末尾加逗号
    "quoteProps": "as-needed", // props 是否用 引号 包裹

    // jsx html 标签是否在同行
    // <span
    // >
    // </span>
    "jsxBracketSameLine": false,

    // 格式化代码的区间
    // "rangeStart": 0,
    //"rangeEnd": 9999,
    // 解析文件类型
    "parser": "babel-ts",
    // 仅格式化带有 @format 、 @prettier 头的文件
    "requirePragma": false,
    // 插入 @format 在文件头部
    "insertPragma": false,
    // 超宽换行
    "proseWrap": "always",
    // strict是所有的空格换行情况都保留，ignore的话就是所有元素间的空格都会被忽略
    // eg. <span> sss </span>
    "htmlWhitespaceSensitivity": "strict",
    // just for vue
    "vueIndentScriptAndStyle": false,
    // 换行标识
    "endOfLine": "lf",
    // 用于 Markdown 等，自动语言识别
    "embeddedLanguageFormatting": "auto"
}
```

项目实际配置

```json
//.prettierrc.json
{
    "semi": false,
    "tabWidth": 4,
    "singleQuote": true,
    "printWidth": 100,
    "trailingComma": "none",
    "arrowParens": "avoid"
}
```
