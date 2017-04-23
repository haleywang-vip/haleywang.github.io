---
layout: post
title: React & Webpack
date: 2015-04-19 23:32:24.000000000 +09:00
---

团队打算开始整体布局React，自已得先研究一下，搞下小demo体验一下。

* 安装webpack

```shell
npm install -g webpack
npm install -g webpack-dev-server
```

* 进入所在项目

```shell
npm init
npm install webpack --save-dev
npm install webpak-dev-server --save-dev
npm install react react-dom --save
npm install react-hot-loader --save-dev
npm install babel-preset-es2015 babel-preset-react --save-dev
npm install babel-core babel-loader --save-dev
npm install style-loader css-loader sass-loader node-sass --save-dev
```

* 配置webpack.config.js

```javascript
module.exports = {
  entry: './main.js',
  output: {
      path: __dirname,
      filename: 'bundle.js'
 },
 module: {
      loaders: [
          { test: /\.js$\/ exclude: /node_modules/, loader: 'babel'},
          { test: /\.scss$/, loader: 'style!css!sass'}
      ]
 }
}
```

* 配置预设.babelrc

```javascript
{
  "presets": ["es2015","react"]
}
```


* comment/CommentForm.js

```javascript
import React from 'react';

class CommentForm extends React.Component {
  render(){
      return(
        <form>
          <div className="container">
              <input type="text" />
          </div>

          <div className="container">
            <input type="submit" />
          </div>
        </form>
      )
  }
}
export { CommentForm as default };
```

* comment/Comment.js

```javascript
import React from 'react';
import CommentForm from './CommentForm';

class Comment extends React.Component {
    render(){
       return(
            <div>
                <h1>评论</h1>
                <CommentForm />
            </div>
        )
    }
 }
export { Comment as default };
```

* main.js

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import Comment from './comment/Comment';

ReactDOM.render(
  <Comment />,
  document.getElementById('app');
)
```

* index.html

```html
<!DOCTYPE html>
<html lang='en'>
<head>
    <meta charset='UTF-8' />
    <title></title>
</head>
<body>
  <div id='app'></div>
 <script src='bundle.js' type='text/javascript'></script>
</body>
</html>
```


* webpack-dev-server --hot --inline

```
http://localhost:8080/webpack-dev-server/index.html
```
