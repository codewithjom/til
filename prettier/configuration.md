# Prettier Configuration

Prettier is **an opinionated code formatter.** It enforces a consistent style by parsing your code and re-printing it with its own rules that take the maximum line length into account, wrapping code when necessary.

Below is a simple configuration that I need on my projects, to have this config file you need to install through `yarn` to install follow the following command:

```sh
yarn add prettier
```

Once done, create a file `.prettierrc` on the root folder of the project and paste this configuration.

```json
{
  "arrowParens": "avoid",
  "singleQuote": true,
  "jsxSingleQuote": true,
  "bracketSpacing": true,
  "semi": false,
  "tabWidth": 2,
  "trailingComma": "none",
  "printWidth": 120
}
```
