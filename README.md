# Angular Library Instructions
How to build Angular library

## Prerequisite
make sure the following are install
- Node.js 10.9.x or later installed.
- Angular CLI V8.x.x or later installed.
- Git

## Steps to Generate Angular Library
- Scaffolding project `ng new <project-name> --create-application=false`
- [Generate library](https://angular.io/cli/generate#library) `ng generate library <library-name> --prefix=<prefix>`
- [Generate Example](https://angular.io/cli/new#ng-new) `ng generate application <library-name-example> --prefix=<prefix> --style=scss`

## [Add Prettier](https://medium.com/@ofirrifo/setup-prettier-with-angular-cli-webstorm-d339097595cf)

Add file `.prettierrc` to root of the project
```js
{
  "singleQuote": true,
  "semi": true,
  "printWidth": 140,
  "tabWidth": 2
}
```

## Add scripts to package.json

## Add License 

## Update README.md file

## Setup Jest
### package.json
1. Remove the following devDependencies
  ```
   "@types/jasmine": "~3.3.15",
   "@types/jasminewd2": "~2.0.3",
   "jasmine-core": "~3.4.0",
   "jasmine-spec-reporter": "~4.2.1",
   "karma": "~4.2.0",
   "karma-chrome-launcher": "~3.0.0",
   "karma-coverage-istanbul-reporter": "~2.1.0",
   "karma-jasmine": "~2.0.1",
   "karma-jasmine-html-reporter": "^1.4.0",
  ```
2. install requierd jest npm packages
   `npm i -D @types/jest jest jest-preset-angular`
3. add to scripts `"lib:test": "jest"`

### add jest.config.js file to the root of the project
```js
module.exports = {
  preset: "jest-preset-angular",
  roots: ['projects/<replace-to-lib-name>/src'],
  setupFilesAfterEnv: ['<rootDir>/projects/<replace-to-lib-name>/src/setup-jest.ts'],
  globals: {
    'ts-jest': {
      tsConfig: '<rootDir>/projects/<replace-to-lib-name>/tsconfig.spec.json'
    },
  },
};
```

### update file `projects/<replace-to-lib-name>/tsconfig.spec.json`
- replace jasmine to jest
- remove "src/test.ts"

**Before**
```js
{
  "extends": "../../tsconfig.json",
  "compilerOptions": {
    "outDir": "../../out-tsc/spec",
    "types": [
      "jasmine",
      "node"
    ]
  },
  "files": [
    "src/test.ts"
  ],
  "include": [
    "**/*.spec.ts",
    "**/*.d.ts"
  ]
}
```

**After**
```js
{
  "extends": "../../tsconfig.json",
  "compilerOptions": {
    "outDir": "../../out-tsc/spec",
    "types": [
      "jest", 
      "node"
    ]
  },
  "files": [],
  "include": [
    "**/*.spec.ts",
    "**/*.d.ts"
  ]
}
```
