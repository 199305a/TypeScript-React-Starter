This repo is now deprecated. In the time since it created [TypeScript support](https://facebook.github.io/create-react-app/docs/adding-typescript) is now a default 
deprecated 不赞成的  
feature of [Create React App](https://facebook.github.io/create-react-app/), [Next.JS](https://nextjs.org) and [Razzle](https://github.com/jaredpalmer/razzle). 
feature 特点
This means you can get started with:

```sh
# Creates an app called my-app
npx create-react-app my-app --typescript

cd my-app

# Adds the type definitions
npm install --save typescript @types/node @types/react @types/react-dom @types/jest

echo "Good to go :tada:"
```

This repo offers some exmples on how to take that project into production and handle testing and state. However, you can
also use the official documentation in the Create React App website for that. 

If you'd like to know more about how to effectively do React with TypeScript, we recommend looking at the following:
effectively 有效的
- [React+TypeScript Cheatsheets](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet#reacttypescript-cheatsheets)
- [React & Redux in TypeScript - Static Typing Guide](https://github.com/piotrwitek/react-redux-typescript-guide#react--redux-in-typescript---static-typing-guide)
- [Use TypeScript to develop React applications](https://egghead.io/courses/use-typescript-to-develop-react-applications)
- [Ultimate React Component Patterns with Typescript 2.8](https://levelup.gitconnected.com/ultimate-react-component-patterns-with-typescript-2-8-82990c516935)
Ultimate 极端的 最重要的

Below is the original README for this sample.

---

# TypeScript React Starter

This quick start guide will teach you how to wire up TypeScript with [React](http://facebook.github.io/react/).
By the end, you'll have

* a project with React and TypeScript
* linting with [TSLint](https://github.com/palantir/tslint)
* testing with [Jest](https://facebook.github.io/jest/) and [Enzyme](http://airbnb.io/enzyme/), and
* state management with [Redux](https://github.com/reactjs/react-redux)

We'll use the [create-react-app](https://github.com/facebookincubator/create-react-app) tool to quickly get set up.
set up 组织结构
We assume that you're already using [Node.js](https://nodejs.org/) with [npm](https://www.npmjs.com/).
assume 假设
You may also want to get a sense of [the basics with React](https://facebook.github.io/react/docs/hello-world.html).
sense 感觉
# Install create-react-app

We're going to use the create-react-app because it sets some useful tools and canonical defaults for React projects.
This is just a command-line utility to scaffold out new React projects.

```shell
npm install -g create-react-app
```

# Create our new project

We'll create a new project called `my-app`:

```shell
create-react-app my-app --scripts-version=react-scripts-ts
```

[react-scripts-ts](https://www.npmjs.com/package/react-scripts-ts) is a set of adjustments to take the standard create-react-app project pipeline and bring 
adjustment 调整  pipeline管道  bring 导致
TypeScript into the mix.

At this point, your project layout should look like the following:

```text
my-app/
├─ .gitignore
├─ images.d.ts
├─ node_modules/
├─ public/
├─ src/
│  └─ ...
├─ package.json
├─ tsconfig.json
├─ tsconfig.prod.json
├─ tsconfig.test.json
└─ tslint.json
```

Of note:

* `tsconfig.json` contains TypeScript-specific options for our project.
  * We also have a `tsconfig.prod.json` and a `tsconfig.test.json` in case we want to make any tweaks to our production builds, or our test builds.
  case 实例 tweak 拧 
* `tslint.json` stores the settings that our linter, [TSLint](https://github.com/palantir/tslint), will use.
* `package.json` contains our dependencies, as well as some shortcuts for commands we'd like to run for testing, previewing, and deploying our app.
shortcuts 捷径
* `public` contains static assets like the HTML page we're planning to deploy to, or images. You can delete any file in this folder apart from `index.html`.
apoart 分割 除去
* `src` contains our TypeScript and CSS code. `index.tsx` is the entry-point for our file, and is mandatory.
mandatory 强制的
* `images.d.ts` will tell TypeScript that certain types of image files can be `import`-ed, which create-react-app supports.

# Setting up source control

Our testing tool, Jest, expects some form of source control (such as Git or Mercurial) to be present.
expect 预期
For it to run correctly, we'll need to initialize a git repository.
correctly 准确的 正确的
```sh
git init
git add .
git commit -m "Initial commit."
```

> Note: if you've cloned this repository, you won't have to run the above at all.

# Overriding defaults

The TSLint configuration that react-scripts-ts sets us up with is a bit overzealous.
overzealous 过分热心的
Let's fix that up.

```diff
 {
-  "extends": ["tslint:recommended", "tslint-react", "tslint-config-prettier"],
+  "extends": [],
+  "defaultSeverity": "warning",
   "linterOptions": {
     "exclude": [
       "config/**/*.js",
       "node_modules/**/*.ts"
     ]
   }
 }
```

[Configuring TSLint](https://palantir.github.io/tslint/usage/configuration/) is out of the scope of this starter, but you should feel free to experiment with something that works for you.
scope 范围 能力 experiment 实验 

# Running the project

Running the project is as simple as running

```sh
npm run start
```

This runs the `start` script specified in our `package.json`, and will spawn off a server which reloads the page as we save our files.
spawn off 导致 引起
Typically the server runs at `http://localhost:3000`, but should be automatically opened for you.
typically 通常 
This tightens the iteration loop by allowing us to quickly preview changes.
tighten 收紧 iteration 迭代 
# Testing the project

Testing is also just a command away:

```sh
npm run test
```

This command runs Jest, an incredibly useful testing utility, against all files whose extensions end in `.test.ts` or `.spec.ts`.
incredibly 难以置信  againt 反对 相反
Like with the `npm run start` command, Jest will automatically run as soon as it detects changes.
detect 发现
If you'd like, you can run `npm run start` and `npm run test` side by side so that you can preview changes and test them simultaneously.
side by side 肩并肩  simultaneously 同时
# Creating a production build

When running the project with `npm run start`, we didn't end up with an optimized build.
Typically, we want the code we ship to users to be as fast and small as possible.
ship 船 
Certain optimizations like minification can accomplish this, but often take more time.
certain 肯定的 minification 压缩率 accomplish 实现
We call builds like this "production" builds (as opposed to development builds).
opposed 截然不同的
To run a production build, just run

```sh
npm run build
```

This will create an optimized JS and CSS build in `./build/static/js` and `./build/static/css` respectively.
respectively 分别 

You won't need to run a production build most of the time,
but it is useful if you need to measure things like the final size of your app.

# Creating a component

We're going to write a `Hello` component.

The component will take the name of whoever we want to greet (which we'll call `name`), and optionally, the number of exclamation marks to trail with (`enthusiasmLevel`).
whoever 那个人 greet 打招呼 问候 exclamation 感叹 mark标记 trail 乡间小道

When we write something like `<Hello name="Daniel" enthusiasmLevel={3} />`, the component should render to something like `<div>Hello Daniel!!!</div>`.
If `enthusiasmLevel` isn't specified, the component should default to showing one exclamation mark.
specify 具体说明 
If `enthusiasmLevel` is `0` or negative, it should throw an error.
negative  #express no #
We'll write a `Hello.tsx`:

```ts
// src/components/Hello.tsx

import * as React from 'react';

export interface Props {
  name: string;
  enthusiasmLevel?: number;
}

function Hello({ name, enthusiasmLevel = 1 }: Props) {
  if (enthusiasmLevel <= 0) {
    throw new Error('You could be a little more enthusiastic. :D');
  }

  return (
    <div className="hello">
      <div className="greeting">
        Hello {name + getExclamationMarks(enthusiasmLevel)}
      </div>
    </div>
  );
}

export default Hello;

// helpers

function getExclamationMarks(numChars: number) {
  return Array(numChars + 1).join('!');
}
```

Notice that we defined a type named `Props` that specifies the properties our component will take.
`name` is a required `string`, and `enthusiasmLevel` is an optional `number` (which you can tell from the `?` that we wrote out after its name).

We also wrote `Hello` as a stateless function component (an SFC).
无状态的
We also wrote `Hello` as a stateless function component (an SFC).
We also wrote `Hello` as a stateless function component (an SFC).
To be specific, `Hello` is a function that takes a `Props` object, and picks apart (or "destructures") all the properties that it will be passed.
pick #to take some things and leave others # apart #separated by a distance or by time  # destructure 破坏 property 资产
If `enthusiasmLevel` isn't given in our `Props` object, it will default to `1`.

Writing functions is one of two primary [ways React allows us to make components]((https://facebook.github.io/react/docs/components-and-props.html#functional-and-class-components)).
If we wanted, we *could* have written it out as a class as follows:

```ts
class Hello extends React.Component<Props, object> {
  render() {
    const { name, enthusiasmLevel = 1 } = this.props;

    if (enthusiasmLevel <= 0) {
      throw new Error('You could be a little more enthusiastic. :D');
    }

    return (
      <div className="hello">
        <div className="greeting">
          Hello {name + getExclamationMarks(enthusiasmLevel)}
        </div>
      </div>
    );
  }
}
```

Classes are useful [when our component instances have some state or need to handle lifecycle hooks](https://facebook.github.io/react/docs/state-and-lifecycle.html).
hook 钩子
But we don't really need to think about state in this specific example - in fact, we specified it as `object` in `React.Component<Props, object>`, so writing an SFC makes more sense here, but it's important to know how to write a class component.
sense 感官
Notice that the class extends `React.Component<Props, object>`.
The TypeScript-specific bit here are the type arguments we're passing to `React.Component`: `Props` and `object`.
Here, `Props` is the type of our class's `this.props`, and `object` is the type of `this.state`.
We'll return to component state in a bit.

Now that we've written our component, let's dive into `index.tsx` and replace our render of `<App />` with a render of `<Hello ... />`.

First we'll import it at the top of the file:

```ts
import Hello from './components/Hello';
```

and then change up our `render` call:

```ts
ReactDOM.render(
  <Hello name="TypeScript" enthusiasmLevel={10} />,
  document.getElementById('root') as HTMLElement
);
```

## Type assertions
assertion 断言 明确确定的
One thing we'll point out in this section is the line `document.getElementById('root') as HTMLElement`.
point out 说明
This syntax is called a *type assertion*, sometimes also called a *cast*.
syntax 句法 cast 全体演员
This is a useful way of telling TypeScript what the real type of an expression is when you know better than the type checker.

The reason we need to do so in this case is that `getElementById`'s return type is `HTMLElement | null`.
Put simply, `getElementById` returns `null` when it can't find an element with a given `id`.
We're assuming that `getElementById` will actually succeed, so we need to convince TypeScript of that using the `as` syntax.
actually 事实 实际上  convince 使确信
TypeScript also has a trailing "bang" syntax (`!`), which removes `null` and `undefined` from the prior expression.
trailing 蔓生 尾随  prior 先前的
So we *could* have written `document.getElementById('root')!`, but in this case we wanted to be a bit more explicit.
explicit 清晰

## Stateful components

We mentioned earlier that our component didn't need state.
mentioned 提及 
What if we wanted to be able to update our components based on user interaction over time?
over 在...之上

At that point, state becomes more important.

Deeply understanding best practices around component state in React are out of the scope of this starter, but let's quickly peek at a *stateful* version of our 
deeply 非常 peek 偷看 
`Hello` component to see what adding state looks like.
looks like 看起来像
We're going to render two `<button>`s which update the number of exclamation marks that a `Hello` component displays.

To do that, we're going to

1. Define a type for our state (i.e. `this.state`)
1. Initialize `this.state` based on the props we're given in our constructor.
1. Create two event handlers for our buttons (`onIncrement` and `onDecrement`).

```ts
// src/components/StatefulHello.tsx

import * as React from "react";

export interface Props {
  name: string;
  enthusiasmLevel?: number;
}

interface State {
  currentEnthusiasm: number;
}

class Hello extends React.Component<Props, State> {
  constructor(props: Props) {
    super(props);
    this.state = { currentEnthusiasm: props.enthusiasmLevel || 1 };
  }

  onIncrement = () => this.updateEnthusiasm(this.state.currentEnthusiasm + 1);
  onDecrement = () => this.updateEnthusiasm(this.state.currentEnthusiasm - 1);

  render() {
    const { name } = this.props;

    if (this.state.currentEnthusiasm <= 0) {
      throw new Error('You could be a little more enthusiastic. :D');
    }

    return (
      <div className="hello">
        <div className="greeting">
          Hello {name + getExclamationMarks(this.state.currentEnthusiasm)}
        </div>
        <button onClick={this.onDecrement}>-</button>
        <button onClick={this.onIncrement}>+</button>
      </div>
    );
  }

  updateEnthusiasm(currentEnthusiasm: number) {
    this.setState({ currentEnthusiasm });
  }
}

export default Hello;

function getExclamationMarks(numChars: number) {
  return Array(numChars + 1).join('!');
}
```

Notice:

1. Much like with `Props`, we had to define a new type for our state: `State`.
1. To update state in React, we use `this.setState` - we don't set it directly except in the constructor. `setState` only takes the properties we're interested in
directly 直接 
updating and our component will re-render as appropriate.
appropriate 适当的 
1. We're using class property initializers with arrow functions (e.g. `onIncrement = () => ...`).
  * Declaring these as arrow functions avoids issues with orphaned uses of `this`.
  declare 声明 avoid 避免 orphaned 孤儿
  * Setting them as instance properties creates them only once - a common mistake is to initialize them in the `render` method which allocates closures one every 
  instance 实例
call to `render`.

We won't use this stateful component any further in this starter.
further 进一步
Stateful components are great for creating components that focus solely on presenting content (as opposed to handling core application state).
solely 唯一的 单独的 presenting 展示 礼物
In some contexts, it can be used for handling your entire application's state, with one central component passing down functions that can call `setState` 
entire 全部的 pass sth down 向后传递  
appropriately; however, for much larger applications, a dedicated state manager might be preferable (as we'll discuss below).
appropriately 适当的    dedicate 尽责  preferable 更好地 
# Adding style 😎

Styling a component with our setup is easy.
To style our `Hello` component, we can create a CSS file at `src/components/Hello.css`.

```css
.hello {
  text-align: center;
  margin: 20px;
  font-size: 48px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.hello button {
  margin-left: 25px;
  margin-right: 25px;
  font-size: 40px;
  min-width: 50px;
}
```

The tools that create-react-app uses (namely, Webpack and various loaders) allow us to just import the stylesheets we're interested in.
various 各种各样的 
When our build runs, any imported `.css` files will be concatenated into an output file.
So in `src/components/Hello.tsx`, we'll add the following import.

```ts
import './Hello.css';
```

# Writing tests with Jest

We had a certain set of assumptions about our `Hello` component.
一定的假设

Let's reiterate what they were:
reiterate 反复 重申
> * When we write something like `<Hello name="Daniel" enthusiasmLevel={3} />`, the component should render to something like `<div>Hello Daniel!!!</div>`.
> * If `enthusiasmLevel` isn't specified, the component should default to showing one exclamation mark.
> * If `enthusiasmLevel` is `0` or negative, it should throw an error.

We can use these requirements to write a few tests for our components.
requirement 依赖 
But first, let's install Enzyme.
[Enzyme](http://airbnb.io/enzyme/) is a common tool in the React ecosystem that makes it easier to write tests for how components will behave.
behave 表现
By default, our application includes a library called jsdom to allow us to simulate the DOM and test its runtime behavior without a browser.
simulate 模仿
Enzyme is similar, but builds on jsdom and makes it easier to make certain queries about our components.

Let's install it as a development-time dependency.

```sh
npm install -D enzyme @types/enzyme enzyme-adapter-react-16 @types/enzyme-adapter-react-16 react-test-renderer
```

Notice we installed packages `enzyme` as well as `@types/enzyme`.
as well as 和...一样的 很好 很满意
The `enzyme` package refers to the package containing JavaScript code that actually gets run, while `@types/enzyme` is a package that contains declaration files 
refer 谈及 提到 
(`.d.ts` files) so that TypeScript can understand how you can use Enzyme.
You can learn more about `@types` packages [here](https://www.typescriptlang.org/docs/handbook/declaration-files/consumption.html).

We also had to install `enzyme-adapter-react-16 and react-test-renderer`.
This is something `enzyme` expects to be installed.

Before writing the first test, we have to configure Enzyme to use an adapter for React 16.
adapter 多功能插头
We'll create a file called `src/setupTests.ts` that is automatically loaded when running tests:

```ts
import * as enzyme from 'enzyme';
import * as Adapter from 'enzyme-adapter-react-16';

enzyme.configure({ adapter: new Adapter() });
```

Now that we've got Enzyme set up, let's start writing our test!
Let's create a file named `src/components/Hello.test.tsx`, adjacent to our `Hello.tsx` file from earlier.
adjacent #very near，next to，or touching #
```ts
// src/components/Hello.test.tsx

import * as React from 'react';
import * as enzyme from 'enzyme';
import Hello from './Hello';

it('renders the correct text when no enthusiasm level is given', () => {
  const hello = enzyme.shallow(<Hello name='Daniel' />);
  expect(hello.find(".greeting").text()).toEqual('Hello Daniel!')
});

it('renders the correct text with an explicit enthusiasm of 1', () => {
  const hello = enzyme.shallow(<Hello name='Daniel' enthusiasmLevel={1}/>);
  expect(hello.find(".greeting").text()).toEqual('Hello Daniel!')
});

it('renders the correct text with an explicit enthusiasm level of 5', () => {
  const hello = enzyme.shallow(<Hello name='Daniel' enthusiasmLevel={5} />);
  expect(hello.find(".greeting").text()).toEqual('Hello Daniel!!!!!');
});

it('throws when the enthusiasm level is 0', () => {
  expect(() => {
    enzyme.shallow(<Hello name='Daniel' enthusiasmLevel={0} />);
  }).toThrow();
});

it('throws when the enthusiasm level is negative', () => {
  expect(() => {
    enzyme.shallow(<Hello name='Daniel' enthusiasmLevel={-1} />);
  }).toThrow();
});
```

These tests are extremely basic, but you should be able to get the gist of things.
extremely 非常      gist 要点
# Adding state management

At this point, if all you're using React for is fetching data once and displaying it, you can consider yourself done.
fetch 吸引 拉取  consider 考虑 斟酌
But if you're developing an app that's more interactive, then you may need to add state management.
interactive 交互
## State management in general

On its own, React is a useful library for creating composable views.
composable 可组合的
However, React doesn't prescribe any specific way of synchronizing data throughout your application.
prescribe 开药方 嘱咐 specific 特性 throughout 自始至终
As far as a React component is concerned, data flows down through its children through the props you specify on each element.
as far as 至于   concerned 担忧
Some of those props might be functions that update the state one way or another, but how that happens is an open question.
an open question 允许讨论的问题


Because React on its own does not focus on application state management, the React community uses libraries like Redux and MobX.

[Redux](http://redux.js.org) relies on synchronizing data through a centralized and immutable store of data, and updates to that data will trigger a re-render of our application.
rely 依赖 trigger 扳机


State is updated in an immutable fashion by sending explicit action messages which must be handled by functions called reducers.
immutable 不可改变的  explicit明确的
Because of the explicit nature, it is often easier to reason about how an action will affect the state of your program.
nature 自然 特性

[MobX](https://mobx.js.org/) relies on functional reactive patterns where state is wrapped through observables and passed through as props.
wrap 包装 pattern 方式 prop 支撑物
Keeping state fully synchronized for any observers is done by simply marking state as observable.
As a nice bonus, the library is already written in TypeScript.
bouns 奖金 红利 

There are various merits and tradeoffs to both.
various 各式各样的 merits优点 tradeoff 权衡
Generally Redux tends to see more widespread usage, so for the purposes of this tutorial, we'll focus on adding Redux;
tend 倾向 widespread 分布广泛的
however, you should feel encouraged to explore both.
encourage 信心满满的
The following section may have a steep learning curve.
follow 在 之后   steep 陡峭的 curve 曲线
We strongly suggest you [familiarize yourself with Redux through its documentation](http://redux.js.org/).

## Setting the stage for actions
stage 阶段 发展时间  
It doesn't make sense to add Redux unless the state of our application changes.
We need a source of actions that will trigger changes to take place.
a source of actions 行动来源 take place 发生
This can be a timer, or something in the UI like a button.

For our purposes, we're going to add two buttons to control the enthusiasm level for our `Hello` component.

## Installing Redux

To add Redux, we'll first install `redux` and `react-redux`, as well as their types, as a dependency.

```sh
npm install -S redux react-redux @types/react-redux
```

In this case we didn't need to install `@types/redux` because Redux already comes with its own definition files (`.d.ts` files).

## Defining our app's state

We need to define the shape of the state which Redux will store.
shape 形状  store 百货商店
For this, we can create a file called `src/types/index.tsx` which will contain definitions for types that we might use throughout the program.
might 可能

```ts
// src/types/index.tsx

export interface StoreState {
    languageName: string;
    enthusiasmLevel: number;
}
```

Our intention is that `languageName` will be the programming language this app was written in (i.e. TypeScript or JavaScript) and `enthusiasmLevel` will vary.
intention 意图 打算  vary 不同呈现差异
When we write our first container, we'll understand why we intentionally made our state slightly different from our props.
intentionally 故意     slightly 略微
## Adding actions

Let's start off by creating a set of message types that our app can respond to in `src/constants/index.tsx`.
start off 以...开始  respond 响应 
```ts
// src/constants/index.tsx

export const INCREMENT_ENTHUSIASM = 'INCREMENT_ENTHUSIASM';
export type INCREMENT_ENTHUSIASM = typeof INCREMENT_ENTHUSIASM;


export const DECREMENT_ENTHUSIASM = 'DECREMENT_ENTHUSIASM';
export type DECREMENT_ENTHUSIASM = typeof DECREMENT_ENTHUSIASM;
```

This `const`/`type` pattern allows us to use TypeScript's string literal types in an easily accessible and refactorable way.
literal 字面的 根本的  accessible 可接近的 refactorable 可重构的
Next, we'll create a set of actions and functions that can create these actions in `src/actions/index.tsx`.

```ts
import * as constants from '../constants';

export interface IncrementEnthusiasm {
    type: constants.INCREMENT_ENTHUSIASM;
}

export interface DecrementEnthusiasm {
    type: constants.DECREMENT_ENTHUSIASM;
}

export type EnthusiasmAction = IncrementEnthusiasm | DecrementEnthusiasm;

export function incrementEnthusiasm(): IncrementEnthusiasm {
    return {
        type: constants.INCREMENT_ENTHUSIASM
    }
}

export function decrementEnthusiasm(): DecrementEnthusiasm {
    return {
        type: constants.DECREMENT_ENTHUSIASM
    }
}
```

We've created two types that describe what increment actions and decrement actions should look like.
We also created a type (`EnthusiasmAction`) to describe cases where an action could be an increment or a decrement.
Finally, we made two functions that actually manufacture the actions which we can use instead of writing out bulky object literals.
manufacture 生产 bulky 庞大而占地方的

There's clearly boilerplate here, so you should feel free to look into libraries like [redux-actions](https://www.npmjs.com/package/redux-actions) once you've got 
clear 清楚地 boilerplate 样板
the hang of things.
the hang of 诀窍


## Adding a reducer

We're ready to write our first reducer!
Reducers are just functions that generate changes by creating modified copies of our application's state, but that have *no side effects*.
generate 引起 生产   modify 修改
In other words, they're what we call *[pure functions](https://en.wikipedia.org/wiki/Pure_function)*.
pure 纯粹的
Our reducer will go under `src/reducers/index.tsx`.
Its function will be to ensure that increments raise the enthusiasm level by 1, and that decrements reduce the enthusiasm level by 1, but that the level never 
falls below 1.
fall 跌落


```ts
// src/reducers/index.tsx

import { EnthusiasmAction } from '../actions';
import { StoreState } from '../types/index';
import { INCREMENT_ENTHUSIASM, DECREMENT_ENTHUSIASM } from '../constants/index';

export function enthusiasm(state: StoreState, action: EnthusiasmAction): StoreState {
  switch (action.type) {
    case INCREMENT_ENTHUSIASM:
      return { ...state, enthusiasmLevel: state.enthusiasmLevel + 1 };
    case DECREMENT_ENTHUSIASM:
      return { ...state, enthusiasmLevel: Math.max(1, state.enthusiasmLevel - 1) };
  }
  return state;
}
```

Notice that we're using the *object spread* (`...state`) which allows us to create a shallow copy of our state, while replacing the `enthusiasmLevel`.
spread 广播 shallow 不深的 
It's important that the `enthusiasmLevel` property come last, since otherwise it would be overridden by the property in our old state.
come 来 过来  since 从此 以后  otherwise 否则 不然 
You may want to write a few tests for your reducer.
Since reducers are pure functions, they can be passed arbitrary data.
arbitrary 随意的
For every input, reducers can be tested by checking their newly produced state.
Consider looking into Jest's [toEqual](https://facebook.github.io/jest/docs/expect.html#toequalvalue) method to accomplish this.
consider仔细考虑 accomplish 完成
## Making a container

When writing with Redux, we will often write components as well as containers.
Components are often data-agnostic, and work mostly at a presentational level.
数据不可知  mostly 通常 presentational 表示层
*Containers* typically wrap components and feed them any data that is necessary to display and modify state.
typically 典型 feed 给 喂养 necessary 必需的
You can read more about this concept on [Dan Abramov's article *Presentational and Container Components*](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0).

First let's update `src/components/Hello.tsx` so that it can modify state.
We'll add two optional callback properties to `Props` named `onIncrement` and `onDecrement`:

```ts
export interface Props {
  name: string;
  enthusiasmLevel?: number;
  onIncrement?: () => void;
  onDecrement?: () => void;
}
```

Then we'll bind those callbacks to two new buttons that we'll add into our component.

```ts
function Hello({ name, enthusiasmLevel = 1, onIncrement, onDecrement }: Props) {
  if (enthusiasmLevel <= 0) {
    throw new Error('You could be a little more enthusiastic. :D');
  }

  return (
    <div className="hello">
      <div className="greeting">
        Hello {name + getExclamationMarks(enthusiasmLevel)}
      </div>
      <div>
        <button onClick={onDecrement}>-</button>
        <button onClick={onIncrement}>+</button>
      </div>
    </div>
  );
}
```

In general, it'd be a good idea to write a few tests for `onIncrement` and `onDecrement` being triggered when their respective buttons are clicked.
respective 各自的 
Give it a shot to get the hang of writing tests for your components.
shot 铅球 射击 投篮 
Now that our component is updated, we're ready to wrap it into a container.
Let's create a file named `src/containers/Hello.tsx` and start off with the following imports.

```ts
import Hello from '../components/Hello';
import * as actions from '../actions/';
import { StoreState } from '../types/index';
import { connect, Dispatch } from 'react-redux';
```

The real two key pieces here are the original `Hello` component as well as the `connect` function from react-redux.
pieces 碎片
`connect` will be able to actually take our original `Hello` component and turn it into a container using two functions:

* `mapStateToProps` which massages the data from the current store to part of the shape that our component needs.
* `mapDispatchToProps` which creates callback props to pump actions to our store using a given `dispatch` function.
pump 泵

If we recall, our application state consists of two properties: `languageName` and `enthusiasmLevel`.
consist 存在
Our `Hello` component, on the other hand, expected a `name` and an `enthusiasmLevel`.
`mapStateToProps` will get the relevant data from the store, and adjust it if necessary, for our component's props.
relevant 紧密相连的 
Let's go ahead and write that.

```ts
export function mapStateToProps({ enthusiasmLevel, languageName }: StoreState) {
  return {
    enthusiasmLevel,
    name: languageName,
  }
}
```

Note that `mapStateToProps` only creates 2 out of 4 of the properties a `Hello` component expects.
Namely, we still want to pass in the `onIncrement` and `onDecrement` callbacks.
namely 也就是说
`mapDispatchToProps` is a function that takes a dispatcher function.
This dispatcher function can pass actions into our store to make updates, so we can create a pair of callbacks that will call the dispatcher as necessary.
dispatcher 调度员  pair 对
```ts
export function mapDispatchToProps(dispatch: Dispatch<actions.EnthusiasmAction>) {
  return {
    onIncrement: () => dispatch(actions.incrementEnthusiasm()),
    onDecrement: () => dispatch(actions.decrementEnthusiasm()),
  }
}
```

Finally, we're ready to call `connect`.
`connect` will first take `mapStateToProps` and `mapDispatchToProps`, and then return another function that we can use to wrap our component.
Our resulting container is defined with the following line of code:

```ts
export default connect(mapStateToProps, mapDispatchToProps)(Hello);
```

When we're finished, our file should look like this:

```ts
// src/containers/Hello.tsx

import Hello from '../components/Hello';
import * as actions from '../actions/';
import { StoreState } from '../types/index';
import { connect, Dispatch } from 'react-redux';

export function mapStateToProps({ enthusiasmLevel, languageName }: StoreState) {
  return {
    enthusiasmLevel,
    name: languageName,
  }
}

export function mapDispatchToProps(dispatch: Dispatch<actions.EnthusiasmAction>) {
  return {
    onIncrement: () => dispatch(actions.incrementEnthusiasm()),
    onDecrement: () => dispatch(actions.decrementEnthusiasm()),
  }
}

export default connect(mapStateToProps, mapDispatchToProps)(Hello);
```

## Creating a store

Let's go back to `src/index.tsx`.
To put this all together, we need to create a store with an initial state, and set it up with all of our reducers.
put 设置
```ts
import { createStore } from 'redux';
import { enthusiasm } from './reducers/index';
import { StoreState } from './types/index';

const store = createStore<StoreState>(enthusiasm, {
  enthusiasmLevel: 1,
  languageName: 'TypeScript',
});
```

`store` is, as you might've guessed, our central store for our application's global state.
gussed 猜测到
Next, we're going to swap our use of `./src/components/Hello` with `./src/containers/Hello` and use react-redux's `Provider` to wire up our props with our container.
wire 金属线 swap 交易
We'll import each:

```ts
import Hello from './containers/Hello';
import { Provider } from 'react-redux';
```

and pass our `store` through to the `Provider`'s attributes:

```ts
ReactDOM.render(
  <Provider store={store}>
    <Hello />
  </Provider>,
  document.getElementById('root') as HTMLElement
);
```

Notice that `Hello` no longer needs props, since we used our `connect` function to adapt our application's state for our wrapped `Hello` component's props.

# Ejecting
驱逐 退出
If at any point, you feel like there are certain customizations that the create-react-app setup has made difficult, you can always opt-out and get the various configuration options you need.
various 各种各样的
For example, if you'd like to add a Webpack plugin, it might be necessary to take advantage of the "eject" functionality that create-react-app provides.

Simply run

```sh
npm run eject
```

and you should be good to go!

As a heads up, you may want to commit all your work before running an eject.
heads up 提醒 
You cannot undo an eject command, so opting out is permanent unless you can recover from a commit prior to running an eject.
undo 解开 opt 挑选 选择 out 出 向外 permanent 永久的  unless 除非 recover 复原 prior 先前的
# Next steps

create-react-app comes with a lot of great stuff.
stuff 物品
Much of it is documented in the default `README.md` that was generated for our project, so give that a quick read.

If you still want to learn more about Redux, you can [check out the official website](http://redux.js.org/) for documentation.
The same goes [for MobX](https://mobx.js.org/).

If you want to eject at some point, you may need to know a little bit more about Webpack.
a little bit 一点

If you want to eject at some point, you may need to know a little bit more about Webpack.
You can check out our [React & Webpack walkthrough here](https://www.typescriptlang.org/docs/handbook/react-&-webpack.html).
walkthrough 演练

At some point you might need routing.
同样的 几点
There are several solutions, but [react-router](https://github.com/ReactTraining/react-router) is probably the most popular for Redux projects, and is often used 
several 一些  probably 大概
in conjunction with [react-router-redux](https://github.com/reactjs/react-router-redux).
conjunction 联合
