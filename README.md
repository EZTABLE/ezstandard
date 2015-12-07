# ezstandard
EZTABLE JavaScript standard

*Please see wiki for installation and editor integration details.*

## Configuration

We use JS standard as our base style, and overwrite couple of rules to meet our consensus.

Add this to your `.eslintrc` file :

```json
{
    "extends": [
        "standard"
    ],
    "rules": {
        "indent": [2, 4, { "SwitchCase": 1 }],
        "space-before-function-paren": [2, "never"]
    }
}
```

## Run Check
To run the style check, you can simply run :

```bash
./node_modules/.bin/eslint .
```

or add this to your `Makefile` :

```
lint:
	./node_modules/.bin/eslint .
```

and run

```bash
make lint
```


## Rules Reference

Basically, we follow the rules of JavaScript Standard Style except the following two :

* **Use 4 spaces** for indentation.

  ```js
  function hello(name) {
      console.log('hi', name)  // ✓ ok
  }

  function hello(name) {
    console.log('hi', name)    // ✗ avoid
  }
  ```

* **DO NOT** add a space before a function declaration's parentheses.

  ```js
  // ✓ ok
  function hello(name) {
      console.log('hi', name)
  }

  // ✗ avoid
  function hello (name) {
      console.log('hi', name)
  }
  ```

For the other rules, please refer to [JavaScript Standard Style Rules](https://github.com/feross/standard/blob/master/RULES.md#semicolons).


## For React Projects

Besides the standard config, we also need to install `eslint-config-standard-react`. This will add React and JSX to work with JavaScript Standard Style.

Here's how to install the packages :

```bash
npm install eslint-config-standard-react eslint-plugin-react --save-dev
```

And this is how your `.eslintrc` file should look like :

```json
{
    "extends": [
        "standard",
        "standard-react"
    ],
    "rules": {
        "indent": [2, 4, { "SwitchCase": 1 }],
        "space-before-function-paren": [2, "never"]
    }
}
```
