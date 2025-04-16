# mlflow-demo
根据流进行对象式编程的-demo
使用nodejs编写
由于还处于概念阶段，就写了个demo，暂时不开放源代码。要是有好的想法，可以提。
目前打算朝severless 云原生方向发展。
可以使用 .\mlflow-? init 初始化example。 
目前只支持 ->单向流。
`````
Usage: mlflow [options] [command]

Minimal serverless flow engine

Options:
  -V, --version   output the version number
  -h, --help      display help for command

Commands:
  init            Initialize a new mlflow project
  run <flow>      Run a specific flow
  help [command]  display help for command
`````
``````
name: example
port: 3000
paths:
  - path: /examplePath
    methods:
      GET:
        logic: |
          -> example
          -> finall
          return: message
      POST:
        logic: |
          -> example
          -> example
          -> finall
          return: message
``````
``````
module.exports = { main };
async function main(input) {
  return input+'1';
}
``````
``````
module.exports = { main };
async function main(cc) {
  return {message: cc};
}
``````
logic里的就是流 
可以使用 .\mlflow-? run flow 运行demo。 
web端口仅输入 input(GET),{"input",data} (POST)
