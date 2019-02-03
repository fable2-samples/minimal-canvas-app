# Fable 2.x Canvas app

This is a simple Fable 2.1 app "hello world" Canvas app.
It does not include Elmish or React.

If you want to see a Fable app including elmish, check [minimal-elmish-react](https://github.com/fable2-samples/minimal-elmish-react).

More sample apps can be found in [fable2-samples](https://github.com/fable2-samples)

## App design

The app simply calls `init` which gets the first `<canvas>` element in the document (`index.html`).

It then sets (mutates) the canvas width and height to a size of `1000` x `800`.
Then it gets the 2D context of the canvas and draws two rectangles, a red and a blue.

## Requirements

- [dotnet SDK](https://www.microsoft.com/net/download/core) 2.1 or higher
- [node.js](https://nodejs.org) with [npm](https://www.npmjs.com/)
- An F# editor like Visual Studio, Visual Studio Code with [Ionide](http://ionide.io/) or [JetBrains Rider](https://www.jetbrains.com/rider/).

## Building and running the app

- Install JS dependencies: `npm install`
- Start Webpack dev server: `npx webpack-dev-server` or `npm start`
- After the first compilation is finished, in your browser open: http://localhost:8080/

Any modification you do to the F# code will be reflected in the web page after saving.

### Paket

Use [Paket](https://fsprojects.github.io/Paket/) to install paket depedencies.
See `.paket` folder for `paket.exe` and config.
On a Mac or Linux, paket needs to be run via [mono](https://www.mono-project.com)
For now, something like:

```bash
$ mono .paket/paket.exe install
Paket version 5.196.0
Resolving packages for group Main:
 - Fable.Core 2.0.3
 - Fable.Import.Browser 1.3.0
 - FSharp.Core 4.6.1
...
```

Or try the included in `paket` npm scripts:

- `npm run paket:mono`

## Project structure

### npm

JS dependencies are declared in `package.json`, while `package-lock.json` is a lock file automatically generated.

### Webpack

[Webpack](https://webpack.js.org) is a JS bundler with extensions, like a static dev server that enables hot reloading on code changes. Fable interacts with Webpack through the `fable-loader`. Configuration for Webpack is defined in the `webpack.config.js` file. Note this sample only includes basic Webpack configuration for development mode, if you want to see a more comprehensive configuration check the [Fable webpack-config-template](https://github.com/fable-compiler/webpack-config-template/blob/master/webpack.config.js).

### F

The sample only contains two F# files: the project (.fsproj) and a source file (.fs) in the `src` folder.

### Web assets

The `index.html` file and other assets like an icon can be found in the `public` folder.
