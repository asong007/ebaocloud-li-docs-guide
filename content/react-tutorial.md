---
title: Build a React App
order: 7
description: Build a new module base on the existing appliation
---
In this toturial, we will create a new module [TODO]

Before you

## 0. Code Structure (TL;TR)
 sub-folds like this:
```bash
├── BrowserHistory/
├── Clause/
├── CompanyIntro/
├── DetailDescription/
├── Disease/
├── Home/
├── PersonalPlan/
├── Plan/
├── ProductDetails/
├── ProductList/
├── Quote/
└── index.js
```
Each fold represents a module (set of pages) of the appliation. The **index.js** is entry app. And in each module fold, there are similar contents like below:

```sh
routes/Home/
      ├── assets/                     # images or other statics
      ├── components/                 # react UI components view or page
      │   ├── HomeView.js             # react component
      │   └── HomeView.scss           # according scss
      ├── containers/                 # redux container that connect view and store
      │   └── HomeContainer.js        # container component, '**only** responsible for wiring in the actions and state necessary to render a presentational component'
      ├── index.js                    # dynamic router entry point
      └── modules/                    # redux modues
          ├── actionTypes.js
          ├── actions.js
          └── reducer.js
```
## 1. Create a new module (very important have read)
   - #### Duplicate one module
     1. Duplicate the **Home** and rename it to **Todo**, and change the according naming as below
        ```bash
        Todo/
          ├── components/
          │   ├── TodoView.js
          │   └── TodoView.scss
          ├── containers/
          │   └── TodoContainer.js
          ├── index.js
          └── modules/
              ├── actionTypes.js
              ├── actions.js
              └── reducer.js
        ```
      2. Edit **components/TodoView.js** as below
        - original:
            ```javascript
            import './HomeView.scss'

            export default class HomeView extends React.Component {
            ```
       - new:
            ```javascript
            import './TodoView.scss'

            export default class TodoView extends React.Component {
            ```
      3. Edit **containers/TodoContainer.js** as below
       - original:
            ```js
            import HomeView from '../components/HomeView'
            ```
       - new:
            ```js
            import HomeView from '../components/TodoView'
            ```


## 2. Parameter

## 3. Call restful APIs

## 4. Represent in UI

## 5. Crossing Modules

## 6. i18n

## 7. awesome apple
## 8. liliang zhu
