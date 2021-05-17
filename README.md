fis3-parser-replacer [![NPM Version](https://img.shields.io/npm/v/fis3-parser-replacer.svg?style=flat)](https://npmjs.org/package/fis3-parser-replacer)
======
> A parser for fis3 to replace string content

## How to use

### Install

```shell
npm install fis3-parser-replacer --save-dev
```

### Add configure to fis-conf.js

```js
// using single replace rule
fis.match('src/**.js', {
    parser: fis.plugin('replacer', {
        from: /xxx/g, // or string
        to: 'xxx'
    })
});

// using multiple replace rules
fis.match('src/**.js', {
    parser: fis.plugin('replacer', {
        rules: [
            {
                from: /xxx/g, // or string
                to: 'xxx'
            },
            {
                from: /xxx/g, // or string
                to: 'xxx'
            }
        ]
    })
});
```

### Options

* from - `string|RegExp`: the regexp or string to replace

* to - `string`: the content to replace from

* rules - `Array.<Object>`: using multiple replace rules, the rule item properties

    * from: the same as `to` option
    
    * to: the same as `from` option

* envify - `boolean`: whether to replace the `process.env.NODE_ENV` with the constant plain string, the string value is determined by the `isProd' option

* isProd - `isProd`: whether in production environment

## Relevant

* [fis3-deploy-replace](https://github.com/fex-team/fis3-deploy-replace)
