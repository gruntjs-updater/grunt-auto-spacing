# grunt-auto-spacing
[![Build Status](https://api.travis-ci.org/sparanoid/grunt-auto-spacing.svg?branch=master)](https://travis-ci.org/sparanoid/grunt-auto-spacing)

> A grunt task which adds CSS classes for paragraphs with leading quotes in HTML

## Getting Started

This plugin requires Grunt `~0.4.1`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-auto-spacing --save-dev
```

One the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-auto-spacing');
```

## The "auto_spacing" task

### Overview

In your project's Gruntfile, add a section named `auto_spacing` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  auto_spacing: {
    options: {
      elements: '*',
      regex: /「|『|“/,
      class: 'leading-indent-fix',
      ignoreClass: 'no-lq',
      addStyle: false,
      addStyleOffset: '-.4em',
      verbose: true
    },
    all: {
      files: {
        'dest-index.html': 'source-index.html',
      },
    },
  },
});
```

### Options

#### elements

Type: `String`
Default: `'*'`

Elements to check, you can define multiple elements by comma-separated values.

```js
grunt.initConfig({
  auto_spacing: {
    all: {
      options: {
        elements: 'p, li'
      },
      files: {
        'dest-index.html': 'source-index.html',
      },
    },
  },
});
```

#### regex

Type: `String`
Default: `/「|『|“/`

Symbols to test, in regex format.

```js
grunt.initConfig({
  auto_spacing: {
    all: {
      options: {
        regex: /「|『|“|‘/
      },
      files: {
        'dest-index.html': 'source-index.html',
      },
    },
  },
});
```

#### class

Type: `String`
Default: `'leading-indent-fix'`

Custom CSS class.

```js
grunt.initConfig({
  auto_spacing: {
    all: {
      options: {
        class: 'lq-fix'
      },
      files: {
        'dest-index.html': 'source-index.html',
      },
    },
  },
});
```

#### ignoreClass

Type: `String`
Default: `'no-lq'`

Elements to be ignored, affected to all descendants.

```js
grunt.initConfig({
  auto_spacing: {
    all: {
      options: {
        ignoreClass: 'no-lq'
      },
      files: {
        'dest-index.html': 'source-index.html',
      },
    },
  },
});
```

#### addStyle

Type: `Boolean`
Default: `false`

Add styles automatically for matched elements.

```js
grunt.initConfig({
  auto_spacing: {
    all: {
      options: {
        addStyle: true
      },
      files: {
        'dest-index.html': 'source-index.html',
      },
    },
  },
});
```

#### addStyleOffset

Type: `String`
Default: `'-.4em'`

Change default styles offset.

```js
grunt.initConfig({
  auto_spacing: {
    all: {
      options: {
        addStyleOffset: '-.39em'
      },
      files: {
        'dest-index.html': 'source-index.html',
      },
    },
  },
});
```

Result:

```html
<p class="leading-indent-fix" style="text-indent: -.39em;">&#x201C;This should be replaced.&#x201D;</p>
```

#### verbose

Type: `Boolean`
Default: `true`

Verbose logging.

## Contributing

In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

## Release History

- See `CHANGELOG.md` for release history