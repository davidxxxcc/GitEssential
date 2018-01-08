# 安裝npm

npm，全名為**N**ode**P**ackage**M**anager，是 Node.js 的套件（package）管理工具，安裝 npm 後，使用

`npm install <module_name>`指令即可安裝新套件，維護管理套件的工作會更加輕鬆。

npm 可以讓 Node.js 的開發者，直接利用、擴充線上的套件庫（packages registry），加速軟體專案的開發。

npm 提供很友善的搜尋功能，可以快速找到、安裝需要的套件，當這些套件發行新版本時，npm 也可以協助開發者自動更新這些套件。

由於現行版本Node.js已經包含了NPM，所以無須額外安裝即可使用，或是使用指令檢查：

```
$ npm -v
5.6.0
```

如果顯示版本編號即是安裝完成。

## 使用 npm 命令安装Module {#使用-npm-命令安装模块}

```
$ npm install <Module Name>
```

（不需輸入&lt;&gt;）將欲安裝的Module名稱替換，例如：

```
$ npm install express
```

# local 本地安裝 與 global 全域安裝

```
npm install express      # local  本地安装
npm install express -g   # global 全域安装
```

其差別在於

——  local  本地安裝

1. 將Module安裝於現在目錄下的/node\_module資料夾內，如果離開此目錄，即失效。
2. 可使用require\(\)，載入Module。

—— global 全域安裝

1. 將Module安裝於 _**/usr/local**_ 。
2. 可以直接在_**Command Line**_使用。
3. 不可使用require\(\)，載入Module。

# 常用指令

npm 不僅可用於安裝新的套件，以下列出部分常用指令。

列出已安裝模組：

```
$ npm ls       # 列出當前目錄下的 Module
$ npm ls -g    # 列出/use/local目錄下的 Module
```

更新 Module：

```
$ npm update express
```

搜尋 Module：

```
$ npm search <Module Name>
```

移除 Module：

```
$ npm search <Module Name>
```



