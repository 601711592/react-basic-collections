
### һ��webpack�������ű�

* 1������package.json����node����Ϣ�ļ���`npm init;`

* 2��package.json��scripts�ű�
	```
	"scripts": {
	    "start": "webpack-dev-server",//ִ��`npm start` �൱��ִ��`webpack-dev-server`��������������
	    "prod": "webpack -p"//ִ��`npm run prod` �൱��ִ��`webpack -p`�������
	}
	```
	

* 3��`Babel`- -����JSX
	```
	npm install --save-dev babel-core;//babel����
	npm install --save-dev babel-loader;	//webpack��babel������
	npm install --save-dev babel-preset-react;	//react��JSX�����js
	```

* 4��`html-webpack-plugin` - - �޸�html�ļ����
`npm install --save-dev html-webpack-plugin`;

* 5��`webpack`��ؿ�
	```
	npm install --save-dev webpack;	//webpack����
	npm install --save-dev webpack-dev-server;	//webpack������
	```
* **

* 6��`.babelrc` - - ����webpack��loader������(babel������)����

	```
	{
	  "presets": [
	    "react"
	  ]
	}
	```
* 7��`webpack.config.js` - - webpack����

```
var HtmlWebpackPlugin = require('html-webpack-plugin');
var HTMLWebpackPluginConfig = new HtmlWebpackPlugin({
  template: __dirname + '/app/index.html', //ָ��htmlģ��Ŀ¼·��
  filename: 'index.html',    //�½��ļ���
  inject: 'body' //<script>[output��filename(index_bundle.js)]</script>�鵽body��,��ɲ�head
});

module.exports = {
  entry: [
    './app/js/app.jsx'    //app.js�������jsx
  ],
  output: {  //ָ�����Ŀ¼������ļ���index_bundle.js
    path: __dirname + '/dist',
    filename: "index_bundle.js"
  },
  module: {
    loaders: [ //������jsx��β���ų�node_modulesĿ¼��babel������
      {test: /\.jsx$/, exclude: /node_modules/, loader: "babel-loader"}
    ]
  },
  plugins: [HTMLWebpackPluginConfig]
};
```

##������ҳindex.html

```
./app/index.html
//html����������<script>��û�С�
//webpack������html-webpack-plugin����Զ�����ת����ƴ�Ӻ��js��<script>��
```

##����jsxԴ�������./app/jsxĿ¼��
����ģ�黯����jsx

##�ġ�ʹ��

1��npm install 
2��bower install

3����������

webpack     //ִ��һ�ο���ʱ�ı���
webpack -p      //ִ��һ�����ɻ����ı��루ѹ����
webpack -w  //�ڿ���ʱ��������������루�ܿ죩

//��Ϊ��package.json������script
npm start //�൱��ִ��`webpack-dev-server`��������������
npm run prod //�൱��ִ��`webpack -p`�������

## �ܽ�

index.html�ļ���webpack����������䣬ÿ�ο���Reactʱ��
ֻ��Ҫ��./app/jsxĿ¼�±�дReact�����jsx���뼴��




