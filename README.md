<h1 align="center">eslint-config-defaults</h1>

<p align="center">
  <a href="https://nodei.co/npm/eslint-config-defaults/">
    <img src="https://nodei.co/npm/eslint-config-defaults.png?compact=true">
  </a>
</p>

<h4 align="center">
  A composable set of ESLint configurations.
</h4>

***

## Installation

Install this config package and ESLint:

```bash
$ npm install --save-dev eslint-config-defaults
```

## Usage

### Full Configurations

This package includes the following complete and ready to use configurations:

- `defaults` - The default ESLint config
- `defaults/configurations/eslint` - The default ESLint config
- `defaults/configurations/walmart` - Config used on Walmart and WalmartLabs projects
- `defaults/configurations/off` - Turns off all rules. This will be ESLint's default after 1.0.0
- `defaults/configurations/es5-browser` - The default ES5 config with browser globals
- `defaults/configurations/es5-node` - The default ES5 config with node globals and rules
- `defaults/configurations/es5-test` - The default ES5 config with mocha globals
- `defaults/configurations/es5` - The default ES5 config
- `defaults/configurations/es6-browser` - The default ES6 config with browser globals
- `defaults/configurations/es6-node` - The default ES6 config with node globals and rules
- `defaults/configurations/es6-test` - The default ES6 config with mocha globals
- `defaults/configurations/es6` - The default ES6 config

To consume and extend a config in ESLint just add the extends attribute to your `.eslintrc`. For
more details about how shareable configs work, see the
[ESLint documentation](http://eslint.org/docs/developer-guide/shareable-configs).

```json
{
  "extends": "defaults"
}
```

```json
{
  "extends": "defaults/configurations/es6-browser"
}
```

### Piecemeal Configurations

ESLint configuration is broken into two parts: `rules` and `environments`

* Rules - The full set of ESLint rules are included in the project broken into categories that
mirror the documentation. Under each rule type there are sets of configuration as well as an
`off.js` file which turns off every rule in this category.

* Environments - Environments are a collection of modifiers that amend a set of generic rules to run
in specific environments like `browser` or `node`.

###### Examples

```json
{
  "extends": [
    "defaults/configurations/es6",
    "defaults/environments/node"
  ]
}
```

```json
{
  "extends": [
    "defaults/rules/eslint/best-practices/default.js",
    "defaults/rules/eslint/errors/default.js"

    "defaults/rules/eslint/es6/off.js"
    "defaults/rules/eslint/legacy/off.js"
    "defaults/rules/eslint/node/off.js"
  ]

  "env" {
    "phantom": true
  }
}
```

***

## License

[MIT License](http://opensource.org/licenses/MIT)
