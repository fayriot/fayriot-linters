# @fayriot/linters
ESlint rules

## Setup
Install from npm
````
npm i @fayriot/linters --save-dev
````

### ESLint + Prettier
Include configurations:

``.eslintrc.js``
````
module.exports = {
    extends: ['./node_modules/@fayriot/linters/eslint'],
};
````

``.prettierrc.js``
````
module.exports = {
    ...require('./node_modules/@fayriot/linters/prettier/prettier.config.js'),
};
````
Add npm-script:
```
"lint": "npm exec -- stylelint --config ./.stylelintrc \"src/**/*.less\" && npm exec -- eslint --config ./.eslintrc.js --debug \"src/**/*.{js,ts,html}\"",
"lint:fix": "npm exec -- stylelint --config ./.stylelintrc --fix \"src/**/*.less\" && npm exec -- eslint --config ./.eslintrc.js --fix --debug \"src/**/*.{js,ts,html}\"",
```

Add ``.eslintignore`` file
```
dist
node_modules
coverage
*.less
*.css
```

### Stylelint
``.stylelintrc``
```
{
    "extends": ["./node_modules/@fayriot/linters/stylelint/stylelint.config.json"],
}
```
Add npm-script:
```
"lint:less": "npm exec -- stylelint --config ./.stylelintrc \"src/**/*.less\"",
"lint:less:fix": "npm exec -- stylelint --config ./.stylelintrc --fix \"src/**/*.less\"",
```
