# 凌云实验室 - 自然语言处理

在线演示：http://lysys.infcn.com.cn/web/lylab

### To run

* You'll need to have [git](https://git-scm.com/) and [node](https://nodejs.org/en/) installed in your system.
* Fork and clone the project:

```
git clone https://github.com/alicoding/react-webpack-babel.git
```

* Then install the dependencies:

```
npm install
```

* Run development server:

```
npm start
```

* Or you can run development server with [webpack-dashboard](https://github.com/FormidableLabs/webpack-dashboard):

```
npm run dev
```

Open the web browser to `http://localhost:3000/`

### To build the production package

```
npm run build
```

### Nginx Config

Here is an example Nginx config:
```
server {
	# ... root and other options

	gzip on;
	gzip_http_version 1.1;
	gzip_types text/plain text/css text/xml application/javascript image/svg+xml;

	location / {
		try_files $uri $uri/ /index.html;
	}

	location ~ \.html?$ {
		expires 1d;
	}

	location ~ \.(svg|ttf|js|css|svgz|eot|otf|woff|jpg|jpeg|gif|png|ico)$ {
		access_log off;
		log_not_found off;
		expires max;
	}
}
```

### Eslint
There is a .eslint.yaml config for eslint ready with React plugin.
To use it, you need to install additional dependencies though:

```
npm install --save-dev eslint eslint-plugin-react
```

To do the actual linting, run:

```
npm run lint
```

### Notes on importing css styles
* styles having /src/ in their absolute path are considered part of the application and exported as local css modules.
* other styles are considered global styles used by many components and are included in the css bundle directly.

### Contribute
Please contribute to the project if you know how to make it better, including this README :)
