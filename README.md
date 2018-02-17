# Create React App

This is a fork of
[Facebook's create-react-app](https://github.com/facebook/create-react-app) that
allows apps to use TypeScript and typed CSS modules.

If something doesn’t work, please [file an issue](https://github.com/jason0x43/create-react-app/issues/new).

## Getting started

```sh
npx create-react-app my-app --scripts-version=@jason0x43/react-scripts
cd my-app
npm start
```

## Differences from create-react-app

The main difference is, of course, TypeScript support in `react-scripts`. A
couple other interesting features are also supported: SVGs and CSS modules.

### CSS modules

To use CSS modules, create files with a `.module.css` extension and import them
into your TypeScript sources as `import * as styles from
'./MyComponent.module.css';`.

### SVGs

The react-scripts will automatically generate React components from SVG files.
These components are essentially inlined versions of the SVGs.

To use this feature, add a typing file to your project with the following contents:

```ts
/// <reference types="react" />

declare module '*.svg' {
  class ReactComponent extends React.Component<any> {}
  export { ReactComponent };
}
```

Then import your SVG files as:

```ts
import { ReactComponent as Something } from '../images/something.svg';
```
