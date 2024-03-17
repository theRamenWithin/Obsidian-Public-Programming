## [Nullish coalescing (??)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing)

This operator returns the value on the right side of the `??` when the left hand value is `null` or `undefined`.
## Examples

Here we have a [`.env`](https://www.npmjs.com/package/dotenv) file and another file that consumes values from the former. Often we set important values in our `.env` file like, API keys, credentials, integration URLs, that our application needs in order to run. If `API_URL` is not defined, we still need to be able to call an API, so we default to calling the production API URL. 

``` dotenv
API_URL=https://api.staging.alexpike.work
```

```typescript
require('dotenv').config();

const apiUrl: string = process.env.API_URL ?? 'https://api.alexpike.work'
console.log(apiUrl)
// Expected output: "https://api.staging.alexpike.work"
```

If our jQuery selector fails to find the given element in the DOM, it will return null. Knowing the product under test, we might be able to assume that because one element is not found, another is present instead.

```Typescript
const menu: JQuery<HTMLElement> = $('div.menu') ?? $('div#sidenav')
```

## [AND (&&)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND)

This operator returns a Boolean. If one or more values are falsy, it will return `false`, otherwise it will return `true`.

## Examples

```typescript
const newFeatureEnabled = useFlag('newFeature);

{newFeatureEnabled && <NewFeature />}
```