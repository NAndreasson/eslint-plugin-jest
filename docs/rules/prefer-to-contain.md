# Suggest using `toContain()` (`prefer-to-contain`)

💼 This rule is enabled in the following
[configs](https://github.com/jest-community/eslint-plugin-jest/blob/main/README.md#shareable-configurations):
`all`, `style`.

🔧 This rule is automatically fixable using the `--fix`
[option](https://eslint.org/docs/latest/user-guide/command-line-interface#--fix)
on the command line.

<!-- end rule header -->

In order to have a better failure message, `toContain()` should be used upon
asserting expectations on an array containing an object.

## Rule details

This rule triggers a warning if `toBe()`, `toEqual()` or `toStrictEqual()` is
used to assert object inclusion in an array

```js
expect(a.includes(b)).toBe(true);
```

```js
expect(a.includes(b)).not.toBe(true);
```

```js
expect(a.includes(b)).toBe(false);
```

### Default configuration

The following patterns are considered warnings:

```js
expect(a.includes(b)).toBe(true);

expect(a.includes(b)).not.toBe(true);

expect(a.includes(b)).toBe(false);

expect(a.includes(b)).toEqual(true);

expect(a.includes(b)).toStrictEqual(true);
```

The following patterns are not considered warnings:

```js
expect(a).toContain(b);

expect(a).not.toContain(b);
```
