![npm](https://img.shields.io/npm/v/react-reveal-effects) ![GitHub Workflow Status](https://img.shields.io/github/workflow/status/tittoh/react-reveal-effects/React%20Reveal%20Effects) ![GitHub issues](https://img.shields.io/github/issues/tittoh/react-reveal-effects) ![Maintenance](https://img.shields.io/maintenance/yes/2022)
# React Reveal Effects

This package is an updated version of [react-reveal](https://github.com/rnosov/react-reveal) by Roman Nosov.
Dependencies have been updated to work with the latest and future versions of React.
#### Fixes
- Upgrade `Babel`
- Add `iframe` support.
- Fix check that `children` is not `null`
- Fix deprecated `componentWillReceiveProps` to `UNSAFE_componentWillReceiveProps`
- Fix css `height` issues


Examples can be found here [React Reveal Examples](https://www.react-reveal.com/)

This is an animation library for React. It's MIT licensed, has a tiny footprint
and written specifically for React in ES6. It can be used to create various cool reveal
on scroll animations in your application.
If you liked this package, don't forget to star
the [Github repository](https://github.com/Tittoh/react-reveal-effects).

## Live Examples

A number of simple effect examples:
- Fade
- Flip
- Rotate
- Zoom
- Bounce
- Roll

## Search Engine Visibility 

`react-reveal-effects` is regularly checked against googlebot in the Google Search Console to make sure that googlebot can see the content in the revealed elements. 

## Installation

In the command prompt run:

```sh
npm install react-reveal-effects --save
```

Alternatively you may use `yarn`:

```sh
yarn add react-reveal-effects
```

## Quick Start

Import effects from [React Reveal Effects](https://www.npmjs.com/package/react-reveal-effects) to your project. Lets try `Zoom` effect first:

```javascript
import Zoom from 'react-reveal-effects/Zoom';
```

Place the following code somewhere in your `render` method: 

```jsx
<Zoom>
  <p>Markup that will be revealed on scroll</p>
</Zoom>
```

You should see zooming animation that reveals text inside the tag. You can change this text to any JSX you want. If you place this code further down the page you'll see that it'd appear as you scroll down.

## Revealing React Components

You may just wrap your custom React component with the effect of your choosing like so:

```jsx
<Zoom>  
  <CustomComponent />
</Zoom>
```

In such case, in the resulting `<CustomComponent />` HTML markup will be wrapped in a `div` tag. If you would rather have a different HTML tag then wrap `<CustomComponent />` in a tag of your choosing:

```jsx
<Zoom>
  <section>
    <CustomComponent />   
  </section>
</Zoom>
```

or if you want to customize `div` props:

```jsx
<Zoom>
  <div className="some-class">
    <CustomComponent />   
  </div>
</Zoom>
```

## Revealing Images

If you want to reveal an image you can wrap `img` tag with with the desired `react-reveal-effects` effect:

```jsx
<Zoom>
  <img height="300" width="400" src="https://source.unsplash.com/random/300x400" />
</Zoom>
```

It would be a very good idea to specify width and height of any image you wish to reveal.

## Children

`react-reveal-effects` will attach a reveal effect to each child it gets. In other words,

```jsx
<Zoom>
  <div>First Child</div>
  <div>Second Child</div>
</Zoom>
```

will be equivalent to:

```jsx
<Zoom>
  <div>First Child</div>
</Zoom>
<Zoom>
  <div>Second Child</div>
</Zoom>  
```

If you don't want this to happen, you should wrap multiple children in a `div` tag:

```jsx
<Zoom>
  <div>
    <div>First Child</div>
    <div>Second Child</div>
  </div>
</Zoom>
```


## Server Side Rendering

`react-reveal-effects` supports server side rendering out of the box. In some cases, when the javascript bundle arrives much later than the HTML&CSS it might cause a flickering. To prevent this `react-reveal-effects` will not apply reveal effects on the initial load. 
Another option is to apply gentle fadeout effect on the initial render. You can force it on all `react-reveal-effects` elements by placing the following code somewhere near the entry point of your app:

```jsx
import config from 'react-reveal-effects/globals';

config({ ssrFadeout: true });
```

Or you you can do it on a per element basis using `ssrFadeout` prop:

```jsx
<Zoom ssrFadeout><h1>Content</h1></Zoom>
```

One last option is to use `ssrReveal` prop. If enabled, this option will suppress both flickering and `ssrFadeout` effect. The unfortunate drawback of this option is that the revealed content will appear hidden to Googlebot and to anyone with javascript switched off. So it will makes sense for images and/or headings which are duplicated elsewhere on the page.

## Forking this package

Fork on github
```
https://github.com/Tittoh/react-reveal-effects
```

Or

Clone the the repository using the following command:

```sh
git clone https://github.com/Tittoh/react-reveal-effects.git
```

In the cloned directory, you can run following commands:

```sh
npm install
```

Install required node modules

```sh
npm run build
```

Builds the package for production to the `dist` folder

```sh
npm test
```

Runs tests

## License

Project source code is licensed under the MIT license.
