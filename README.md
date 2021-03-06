# Disallow wildcard targets for postMessage (no-wildcard-postmessage)

![CI](https://github.com/movableink/eslint-plugin-no-wildcard-postmessage/workflows/CI/badge.svg)

This function disallows unsafe coding practices that may result into security vulnerabilities.
We will postMessage calls that contain a target origin of `"*"`.

## Rule Details

Disallowed:

```js
frame.postMessage(obj, '*');
```

A few examples of allowed practices:

```js
frame.postMessage(obj, 'http://domain.tld');
// in a worker:
postMessage(obj);
```

This rule is being used within Mozilla to maintain and improve the security of the Firefox OS front-end codebase _Gaia_. Further documentation, which includes references to the escaping functions can be found on [MDN](https://developer.mozilla.org/en-US/Firefox_OS/Security/Security_Automation).
