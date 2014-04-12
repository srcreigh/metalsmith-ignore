
# metalsmith-ignore

  A Metalsmith plugin to ignore files that match a pattern.

## Installation

    $ npm install metalsmith-ignore

## CLI Usage

  Install via npm and then add the `metalsmith-ignore` key to your `metalsmith.json` plugins. The simplest case just ignores a single pattern:

```json
{
  "plugins": {
    "metalsmith-ignore": "drafts/*"
  }
}
```

  But you can also pass an array of patterns to ignore:

```json
{
  "plugins": {
    "metalsmith-ignore": [
      "drafts/*",
      "unfinished/*"
    ]
  }
}
```

  This plugin uses [minimatch](https://github.com/isaacs/minimatch) to match files. If you want to specify options to minimatch, you can use the object constructor:

```json
{
  "plugins": {
    "metalsmith-ignore": {
      "patterns": "*.swp",
      "options": {
        "matchBase": true,
        "dot": true
      }
    }
  }
}
```

```json
{
  "plugins": {
    "metalsmith-ignore": {
      "patterns": [
        "*.swp",
        "drafts/*"
      ],
      "options": {
        "matchBase": true,
        "dot": true
      }
    }
  }
}
```

## Javascript Usage

  Pass the options to `Metalsmith#use`:

```js
var ignore = require('metalsmith-ignore');

metalsmith.use(ignore('drafts/*'));
```

  You can also pass an array of patterns to ignore:

```js
var ignore = require('metalsmith-ignore');

metalsmith.use(ignore([
  'drafts/*',
  'unfinished/*'
]));
```

  And lastly you may pass options to the matching algorithm:

```js
var ignore = require('metalsmith-ignore');

metalsmith.use(ignore({
  'patterns': '*.swp',
  'options': {
    'matchBase': true,
    'dot: true
  }
}));
```

```js
var ignore = require('metalsmith-ignore');

metalsmith.use(ignore({
  'patterns': [
    '*.swp',
    'drafts/*'
  ],
  'options': {
    'matchBase': true,
    'dot: true
  }
}));
```

## License

  MIT
