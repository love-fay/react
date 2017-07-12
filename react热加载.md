# react热加载
1. 在没有使用相关插件之前，以我开发为例，只用<pre>webpack-dev-server --inline</pre>时候，当组件经过更改保存后，页面会进行重新刷新，如果是简单的应用这样做可以，但是一旦复杂起来，重新刷新后就不得不经过很多操作后回到之前的状态，显然这样的情况是我们不愿意看到的，而且大大降低了开发效率，所以我这里选择了<font color=green>babel-preset-react-hmre</font>，利用它便可以实现局部刷新。
2. 于是安装它，<pre>npm install babel-preset-react-hmre --save-dev</pre>，它主要依赖于<font color=green>react-transform-hmr</font>、<font color=green>react-transform-catch-errors</font>。react-transform-hmr用来实现上面的热加载，而react-transform-catch-errors用来捕获错误，直接展示在页面上，而不用在去控制台查找错误。
3. 配置.babelrc
	<pre>
	{
	  "presets": [
	    "es2015",
	    "react",
	    "stage-0"
	  ],
	  "env": {
	    "development": {
	      "presets": [
	        "react-hmre"
	      ]
	    }
	  }
	}
	</pre>
4. 启动<pre>webpack-dev-server --inline --hot</pre>。
