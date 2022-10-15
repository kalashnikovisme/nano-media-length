# nano-metadata [![Linter](https://github.com/kalashnikovisme/nano-metadata/actions/workflows/linter.yml/badge.svg?branch=main)](https://github.com/kalashnikovisme/nano-metadata/actions/workflows/linter.yml) [![Test](https://github.com/kalashnikovisme/nano-metadata/actions/workflows/test.yml/badge.svg?branch=main)](https://github.com/kalashnikovisme/nano-metadata/actions/workflows/test.yml)
Get duration of video file in browser

[Why do tests fail?](https://github.com/kalashnikovisme/nano-metadata#why-do-tests-fail)

# Install

```
npm install nano-metadata
```

or

```
yarn add nano-metadata
```

# Usage

## Video duration

```javascript
import { video } from 'nano-metadata'

change(e) {
  const file = e.target.files[0]
  
  video.duration(file).then((duration) => {
    console.log(duration) // will show you video duration in seconds
  })
}
```

# Features

| | Video  | Audio |
| ------------- | ------------- | ------------- |
| Duration  | ✅ | ❌ |
| *other features?* | | |

# Contribute

1. Clone repo `git clone git@github.com:kalashnikovisme/nano-metadata`
2. Run `yarn`
3. To run tests `make test`
4. To run linter `make linter`

## Why do tests fail?

This package uses `onloadedmetadata` event to store video duration. We use [js-dom](https://github.com/jsdom/jsdom) for web implementation in the tests. Looks like it does not support this event for now.

### Solutions

We will rewrite tests with chrome headless and selenium soon
