# maprover--api-tsjs-infer
Expose models with a lambda function through API Gateway


##To deploy:

1. Install serverless plugins:
```
serverless plugin install -n serverless-python-requirements
serverless plugin install -n serverless-reqvalidator-plugin
serverless plugin install -n serverless-aws-documentation
serverless plugin install -n serverless-plugin-custom-roles
```

2. Install node tensorflow module:
```
npm install @tensorflow/tfjs
```

3. Useful
    - run local test: ```sls invoke local -f infer```

4. Sources:
    - [aws nodejs canva](https://github.com/Automattic/node-canvas/wiki/Installation:-AWS-Lambda)
    - [node-canva](https://github.com/Automattic/node-canvas)
    - [problems with lambda so libs](https://github.com/Automattic/node-canvas/issues/680)

5. Lambda Tricks:
    - list files on the running machine
```
const fs = require('fs');

exports.handler = async (event, context) => {
  return fs.readdirSync("/usr/lib64").filter(p => p.match(/\.so/)).sort().join("\n");
};
```
