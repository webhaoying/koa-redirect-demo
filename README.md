# Fetch Redirect Demo

What will happen if fetch an endpoint but the endpoint returns 302? Run this little demo to find out!
# 另外，关于node服务的代码，都可以在此项目进行实践操作。

# Installation

Needs node 8+

    nvm install 8

    npm install

    npm start

Visit: http://localhost:3000/ and check out the network requests.

# License

No license, you can use it anywhere you like.


当eslint 具体的文件的时候，有错误就会抛出，抛出的code有 0、1、2 之分 
#### Exit codes
  When linting files, ESLint will exit with one of the following exit codes:

0: Linting was successful and there are no linting errors. If the --max-warnings flag is set to n, the number of linting warnings is at most n.
1: Linting was successful and there is at least one linting error, or there are more linting warnings than allowed by the --max-warnings option.
2: Linting was unsuccessful due to a configuration problem or an internal error.
[eslint文档](https://eslint.org/docs/user-guide/command-line-interface#exit-codes).
### pre-commit
package.json 配置如下
其中exit 0 代表正常退出，脚本继续向下执行，
exit 1  代表异常退出，脚本不再向下执行。
可以利用pre-commit来达到提交代码的时候，有错误或者告警不可提交的目的
```
  "scripts": {
      "start": "node index.js",
      "test": "echo \"Error: no test specified\" && exit 0",
      "test-right": "echo \"正常退出\" && exit 0"
  },
  "pre-commit": [
    "test-right",
    "test"
  ],
```