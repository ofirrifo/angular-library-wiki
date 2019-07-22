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
