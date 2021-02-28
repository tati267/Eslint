# Code formatters
Practical implementation **Eslint**, **Husky**, **Lint staged** 

## Eslint, Prettier
Lesson https://www.udemy.com/course/modern-javascript-from-beginning/

### Setting

``` shell 
$ npm init -y
$ npm i --save-dev eslint
$ npm i --save-dev eslint-config-airbnb
$ npm i --save-dev eslint-config-prettier
$ npm i --save-dev eslint-plugin-html
$ npm i --save-dev eslint-plugin-import
$ npm i --save-dev eslint-plugin-prettier
$ npm i --save-dev prettier
```
Create in folder of your project file *.eslintrc* with set of configurations which we going to use in eslint

``` js
{
"extends": ["airbnb/base"]
}
```

and file *.eslintgitignore*

``` js
node_modules
/.vscode
/.git
```
Also in *package.json* change scripts:

``` js
  "scripts": {
    "lint": "eslint ./src",
    "lint-fix": "eslint ./src --fix"
  },
```

### Use
In Terminal to start eslint (to find all mistakes)


``` shell 
$ npm run lint
```

and finally to correct mistakes: 

``` shell 
$ npm run lint-fix
```

## Husky, Lint staged

### Setting

``` shell 
$ npm i --save-dev husky lint-staged
```
In *package.json* add script:

```  js
"husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "*.js": [
      "npm run lint:fix",
      "git add"
    ]
  }
  ```