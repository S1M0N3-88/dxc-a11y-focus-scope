# a11y-focus-scope

> Accessibility util for scoping focus to an element.

## Installation

```sh
$ npm install --save a11y-focus-scope
```

## Import

In SystemJS configuration file add the following line in paths:

```js
'eng-a11y-focus-scope': 'node_modules/eng-a11y-focus-scope/index.js'
```

In your Component add the following lines in imports:

```js
import {scopeFocus, unscopeFocus} from 'eng-a11y-focus-scope';
```

## Usage

```js
document.body.innerHTML = `
  <button id="outer-button">Outer Button</button>

  <div id="container">
    <button id="inner-button">Inner Button</button>
  </div>
`;

var container = document.getElementById('container');
var innerButton = document.getElementById('inner-button');
var outerButton = document.getElementById('outer-button');

scopeFocus(container);
// document.activeElement === container;

innerButton.focus();
// document.activeElement === innerButton;

outerButton.focus();
// document.activeElement === container;

unscopeFocus();
outerButton.focus();
// document.activeElement === outerButton;
```
