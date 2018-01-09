# Express

在開發本專案時，為學習Node.js Server架設以及學習專案架構，採用Express Module；前端模板使用ejs。

在全域安裝\(任何路徑下\) express, 並使用 _**最高權限使用者** _安裝 express-generator 使用下列指令來安裝 express：

```
$ sudo npm install express -g            # 使用 最高權限者 安裝
$ sudo npm install express-generator -g  # 使用 最高權限者 安裝
```

使用 -h 選項來 確認 Express 已安裝， 同時顯示指令選項：

```
$ express -h
```

確定安裝完成後，開始建立第一個專案：

舉例來說，以下是在現行工作目錄中建立一個名為 myapp 的 Express 應用程式：

```
$ express --view=ejs myapp
```

然後安裝相依項目：

```
$ cd myapp 
$ npm install
```

使用下列指令來執行應用程式：

```
$ npm start
```

\# 執行後，欲離開 按按鍵 control + c \(不是command鍵\)

\# 然後在瀏覽器中載入 [http://localhost:3000/](http://localhost:3000/)_** **_，以查看輸出。

產生的應用程式具有如下的目錄結構：

```
    .
    ├── app.js
    ├── bin
    │   └── www
    ├── package.json
    ├── public
    │   ├── images
    │   ├── javascripts
    │   └── stylesheets
    │       └── style.css
    ├── routes
    │   ├── index.js
    │   └── users.js
    └── views
        ├── error.pug
        ├── index.pug
        └── layout.pug
```

# package.json

package.json檔的用途是紀錄該專案的名稱、憑證、啟動方式、相依模組等等。

_**DEMO**_

```
{
  "name": "express-login",
  "version": "0.0.0",
  "private": true,
  "scripts": {
    "start": "node ./bin/www"
  },
  "dependencies": {
    "body-parser": "~1.18.2",
    "cookie-parser": "~1.4.3",
    "debug": "~2.6.9",
    "ejs": "~2.5.7",
    "express": "~4.15.5",
    "morgan": "~1.9.0",
    "serve-favicon": "~2.4.5"
  }
}
```



