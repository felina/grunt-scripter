# grunt-scripter

> Autoinsert script tags (or other filebased tags) in an html file

## Getting Started
This plugin requires Grunt `~0.4.x`

When the task is run the destination file(s) is updated with script tags pointing to all the source files. The reason this plugin was built was to automate the process of inserting script tags when building large web apps.

```shell
npm install grunt-scripter --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-scripter');
```

## The "scripter" task

### Overview
In your project's Gruntfile, add a section named `scripter` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  scripter: {
    defaultOptions: {
      options: {
        startTag: '<!--SCRIPTS-->',
        endTag: '<!--SCRIPTS END-->',
        fileTmpl: '<script src="%s"></script>',
        appRoot: 'app/'
      },
      files: {
        // Target-specific file lists and/or options go here.
        'app/index.html': ['app/scripts/**/*.js']
      },
    },
  },
})
```

### Options

#### options.startTag
Type: `String`
Default value: `'<!--SCRIPTS-->'`

Script tags are places between the startTag and endTag

#### options.endTag
Type: `String`
Default value: `'<!--SCRIPTS END-->'`

Script tags are places between the startTag and endTag

#### options.fileTmpl
Type: `String`
Default value: `'<script src="%s"></script>'`

The template used to insert the reference to the script files.

#### options.appRoot
Type: `String`
Default value: `''`

The root of the application. Script links are relative from this folder.

#### options.relative
Type: `Boolean`
Default value: `false`

Reference files using a relative url.
