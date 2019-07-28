#1.新建项目文件夹

在新建项目中依次运行以下代码：
```
npm init 

git init
git add README.md
git commit -m 'add Readme'
git remote add origin git@github.com:WangYP1996/ReactWebpack.git
git push -u origin master //第一次使用手动方式向git添加文件，以免出现莫名其妙的错误，之后用vscode添加

npm install babel
npm i webpack webpack-cli -D
npm i webpack-dev-server

npm i react react-dom --save
```
修改package.json文件，修改script内容如下：
```
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack",
    "dev": "webpack-dev-server"
},
```

#2.安装依赖项
安装如下依赖项：
```
npm i babel-loader

npm i @babel/core -D
npm i @babel/preset-react
```
修改webpack.config.js，加入如下内容：
```
module: {
        rules: [
            {
                test: /\.(js|jsx)$/,
                exclude: /node_modules/,
                use: {
                    loader: 'babel-loader'
                }
            }
        ]
    }
```
根目录下新建.babelrc，内容如下：
```
{
    "presets": ["@babel/react"]
}
```
src目录下新建index.js，内容如下：
```
import React from 'react';
import ReactDom from 'react-dom';

ReactDom.render (
    <div>Hello React!</div>,
    document.getElementById('app')  
);
```