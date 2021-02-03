issue1:
	ReactDOM.render(
	  <React.StrictMode>
	  	<App />
	  </React.StrictMode>,
	  document.getElementById('root')
	);

	react引入antd之后报错，需要删除<React.StrictMode>
	
issue2: 
	https://blog.csdn.net/J_Y_X_8/article/details/71827548
	react项目中引用AntDesign组件库时，在运行项目报一下警告：
	You are using a whole package of antd, please use https://www.npmjs.com/package/babel-plugin-import to reduce app bundle size.
	
	执行：npm i babel-plugin-import -D
	
	根目录下新建.roadhogrc文件（别忘了前面的点，这是roadhog工具的配置文件，下面的代码用于加载上一个命令安装的import插件），写入：
	
	{
	  "extraBabelPlugins": [
	    ["import", {
	      "libraryName": "antd",
	      "libraryDirectory": "lib",
	      "style": "css"
	    }]
	  ]
	}
