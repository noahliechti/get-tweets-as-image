# Get screenshots of Tweets with Puppeteer API

**Hint** To run puppeteer on Heroku I needed to add the `puppeteer heroku buildpack`.

## Start server (http://localhost:3000)

```bash
npm i
npm run start
```

## Fetch Data

```js
fetch(
  `http://localhost:3000/get-image?tweetURL=${state.tweetURL}&language=${state.language}&theme=${state.theme}`
)
  .then((payload) => payload.json())
  .then((data) => {
    const { image } = data;
    // Do something with the image
  })
  .catch((err) => {
    console.log("ERROR. Something went wrong.", err);
  });
```

### Valid themes

- "dark" / "light"

### Languages example

- en
- de
- nl
- it
- ...

### Tweet URL example

- https://twitter.com/elonmusk/status/1483633282482847744

## Use image in jsx

```jsx
<img src={`data:image/png;base64,${imageData}`} alt="tweet" />
```
