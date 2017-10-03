# eBaoCloud Sales Frontend Architecture

## 1. Technologies
- [React Redux Starter Kit](https://github.com/davezuko/react-redux-starter-kit)
- [React](https://facebook.github.io/react/)
- [React Router](https://github.com/ReactTraining/react-router)
- [ES6](https://github.com/lukehoban/es6features)
- [Redux](http://redux.js.org/)

## 2.	IDE and debug tools
- [VS Code](https://code.visualstudio.com/docs/nodejs/reactjs-tutorial) or [WebStorm](https://blog.jetbrains.com/webstorm/2015/10/working-with-reactjs-in-webstorm-coding-assistance/)
- Chrome and Redux chrome plugin (google app store)
![Chrome Redux Plugin](/md-resource/chrome-redux-plugin.png)

## 3.	Main 3rd part UI libraries
- 1)	animate.css
- 2)	material-ui
- 3)	react-addons-css-transition-group
- 4)	react-loader-advanced
- 5)	react-pull-to-refresh
- 6)	react-signature-canvas
- 7)	react-tap-event-plugin
- 8)	react-waypoint
- 9)	react-weui

## 4.	Main 3rd part tools
- 1)	moment
- 2)	numeral
- 4)	history
- 5)	mobile-detect

## 5.	Main 3rd part dev build tools
- 1)	express
- 2)	webpack
- 3)	babel
- 4)	node-sass
- 5)	grunt
- 6)	i18next-extract-gettext

## 6.	Layout & CSS solution
- 1)	amfe-flexible
- 2) sass
- 3)	rem
- 4)	flex box

## 7.	Setup
- 1)	Install Node.js
- 2)	On windows run below in CMD:
  - ```npm install --global --production windows-build-tools```
- 3)	In project root folder run:
  - ```npm install```
- 4)	To run dev:
  - ```npm start```
- 5) In Chrome visit:
  - [click here ](localhost:3000/app/productList?msg=eyJ0ZW5hbnRDb2RlIjoiR1VFU1QiLCJwcm9kdWNlckNvZGUiOiJhdjEyMzQ1IiwicHJvZHVjZXJOYW1lIjoiQXZyaXN0IEFnZW50IiwicHJvZHVjZXJUeXBlIjoiMSIsInByb2R1Y2VyUGhvbmUiOiIxMjM0NTY3ODkwMSIsInByb2R1Y2VyRW1haWwiOiJhZG1pbkBlYmFvdGVjaC5jb20iLCJleHRyYVByb3BlcnRpZXMiOnt9LCJhZ2VudEluZm9NYXAiOnt9fQ==&sign=14222f754cf86d06cd1f462d8ce91278&tenantCode=GUEST)
- 6)	To build release package
  - a.	UAT build: ```npm run build:uat```
  - b.	Production build: ```npm run build```

## 8.	Naming conventions
- 1)	All varialbes, parameters, properties, functions and files names should follow Camel Case
- 2)	All class names and react component js file names should follow Pascal Case
- 3)	All const strings should follow UPPER_CASE_WITH_UNSERSCORE
- 4)	All naming should be self-descriptive, more detail would be better.

## 9.	Folder structure
/root path | comments
--------------- | ------------------
i18nProcess.txt |	i18n process guide
Gruntfile.js |	i18n grunt tasks config
gettext0.19.8.1-iconv1.14-shared-64.exe |	Windows msgmerge tool of gettext
project.config.js	|	project level build config
/build/ |	All build-related code
/server/ |	Express application that provides webpack middleware
/public/ |	Static public assets (not imported anywhere in source code)
/translations/ |	GNU gettext i18n translation files
/src/ |	source code folder, see below

## 10.	src code folder structure
/ | root path
--------------- | ------------------
main.js |	webpack entry point of js
index.html |	webpack entry point of html template
config.js	app | config (should also be packed into bundle)
/common/ |	common utils
action.js |	common loading handle actions
history.js |	overwritten browser history with base name ‘app’
request.js |	simplify es6 fetch
resource.js |	static resource utils
share.js |	overwritten share button behavior by different use case
utils.js |	util functions
/companies/ |	company components for special inputs and flow during proposal, company code is folder name, CompanyComponents should be customized by each insurer and could have:
FormJob |	optional, UI component return jobClass and jobCode, if no then job is not required
FormAddress |	optional, UI component return an address region object, if no then region is not required
BankFormGroup |	optional, UI component return bank account object, if no then choose other payment method rather than bank card transfer
ProposerQuestionnaire |	optional, proposer questionnaire, if no then skip this step
InsuredQuestionnaire |	optional, insured questionnaire, if no skip this step
InsuredProposerRelations |	required, code of insured ph relation, self must be 1
BeneficiaryInsuredRelations |	optional, code of bene insured relation, if no then legal
CertiTypes |	required, code of certification card type, 1 is Chinese ID card now
MarriageStatuses |	optional, code of marriage status, if no then marriage status is not required
DocumentTypes |	optional, which proposal documents should have, if no skip material collection and signature page, need more design
NoticeAndPrompt |	optional, usually customer should agree some warnings and notices during proposal process in China
AddressData |	optional, address data to show region name in check order page
BankData |	optional, bank data to show bank name in check order page
BankAddressData |	optional, address data to show bank account registered city
NeedWorkplace |	optional, if ph and insured need company input
NeedHeightAndWeight |	optional, if ph and insured need height and weight
NeedIncomeAndSource |	optional, if ph need income and source
/components/ |	common UI components
Dialog/ |	Alert.js and Confirm.js
Form/ |
BankFormGroup.js |	default Chinese bank form group
FormAddress.js |	default region picker
FormDate.js |	an select with popup date picker
FormField.js |	common form field wrapper with left label
FormGroup.js |	form group with icon, title and an action button
FormInput.js |	input with type
FormRadio.js |	a better radio button group
FormSelect.js |	select with options
FormSwitch.js |	a toggle
FormText.js |		static text with label
FormTextarea.js |	1st line is label and next line is a full with textarea
Header/ |	page header with back icon
Modal/ |	a sized center modal with title, body and close button
NativeImageUpload/ |	UI with default image and on click handler
NavTab/ |	navigation tab
Pikcer/ |
AddressPicker.js |	a slide up 3 level province/city/region picker
DatePicker.js |	a slide up 3 level yyyy/MM/dd date picker
JobPicker.js |	a slide up 3 level big/small/slight job picker
Picker.js |	a slide up picker
PropupAddressPicker.js |	AddressPicker with popup
PopupDatePicker.js |	DatePicker with popup
PopupJobPicker.js |	JobPicker with popup
Selector.js	|	a slide up select based on Picker
Popup/ |
Alert.js |	a better alert
Layer.js |	a popup layer with transparent background
Pop.js |	a full scree modal dialog with title and bottom close button
PopupSelector.js |	a popup slide up selector with title, confirm and cancel buttons
Tip.js |	a toast show message 3 seconds and disappear with animation
Toast.js |	a center loading circle written by css
Question/ |	common question UI component with a toggle and sub question textarea
SearchBar/ |	overwrite react-weui SearchBar
Signature/ |	signature UI component
Steps/ |	step bar
Tag/	|	tag.js and tagGroup.js
/i18n/ |	localized strings
/layouts/ |	page layout, can add page in and out animation
/routes/ |	web app page router and business module
Clause/ |	life product term page
CompanyIntro/ |	insurer intro page
DetailDescription/ |	life product detail info page
Disease/ |	liability disease page
Home/ |	a template of a route
PersonalPlan/ |	user quotation list page
Plan/ |	quotation view page
ProductDetails/ |	sales product detail info page
ProductList/ |	sales product list
Quote/ |	quote and proposal pages
/store/ |	Redux-specific pieces
createStore.js |	Create and instrument redux store
reducers.js |	Reducer registry and injection
/styles/ |	Application-wide styles (generally settings)

## How Redux work
![Redux Action Flow](/md-resource/redux-action-flow.png)
![Redux Data Flow](/md-resource/redux-data-flow.png)

## 11.	routes child folder code structure, module name is folder name
components/ |	react UI components view or page
--------------- | ------------------
containers/ |	redux container that connect view and store
modules/ |	redux modues
action.js |	redux private actions, public actions and async actions
actionType.js |	action type used by action and reducer
reducer.js |	redux reducer that save or modify data map to view
index.js |	dynamic router entry point

## 12.	How to create a router page for a new module
- 1)	Copy a template module folder that named “Home”, rename it to your module name, such as “Xxx”
- 2)	In components/ folder, change the root view name from ‘HomeView.js’ to what you wanted (such as ‘XxxView.js’), change the sass file name from ‘HomeView.scss’ (such as ‘XxxView.scss’) to what you wanted. Change the view name in below line:
```js
export default class HomeView extends React.Component
```
- 3)	In containers/ folder, change the root container name from ‘HomeContainer.js’ to what you wanted (such as ‘XxxContainer.js’). Change the file import in below line:
```js
import HomeView from '../components/HomeView'
```

Now no need to change modules/ folder yet
- 5)	In index.js, add a path for this module such as:
path: 'xxx/:requiredPathParam(:/optionalPathParam)',

- 6)	Change the import corresponding such as:
```js
import { injectReducer } from '../../store/reducers'
export default (store) => ({
  path: 'xxx/:requiredPathParam(:/optionalPathParam)',
  /*  Async getComponent is only invoked when route matches   */
  getComponent (nextState, cb) {
    /*  Webpack - use 'require.ensure' to create a split point
     and embed an async module loader (jsonp) when bundling   */
    require.ensure([], (require) => {
      /*  Webpack - use require callback to define
       dependencies for bundling   */
      const Xxx = require('./containers/XxxContainer').default
      const reducer = require('./modules/reducer').default

      /*  Add the reducer to the store on key 'xxx'  */
      injectReducer(store, { key: 'xxx', reducer })

      /*  Return getComponent   */
      cb(null, Xxx)

      /* Webpack named bundle   */
    }, 'xxx')
  }
})
```

- 7) Add it into /routes/index.js:
```js
  childRoutes : [
    Xxx(store),
    ...
  ]
```

- 8) To test it, in Chrome visit http://localhost:3000/app/xxx/pathParam

## 13.	How to get path param and query parameter from URL in view
- 1)	Path parameter (/:pathParam) such as:
```js
let pathParam = this.props.params.pathParam,
```
- 2)	Query parameter (?queryParam=) such as:
```js
let queryParam = this.props.location.query.queryParam;
```

## 14.	How to call an data action from view to fetch data from a rest service
- 1)	In reducer.js, add data model you want to save to store which returns from rest service, such as:
```js
// data store from backend
const initDataState = {
  restReturnObject: null
}
function data(state = initDataState, action) {
  switch (action.type) {
    default:
      return state
  }
}
```

- 2)	In actionTypes.js add an action type that describe what will will happen to modify store tree, module action name must start with ‘Xxx/’ (global action could have not prefix), such as:
```js
export const RECEIVE_REST_RETURN_OJBECT = 'xxx/RECEIVE_REST_RETURN_OJBECT'
```

- 3)	In actions.js add a private action:
```js
function setRestReturnObject (restReturnObject) {
  return {
    type: t.RECEIVE_REST_RETURN_OJBECT,
    restReturnObject,
    receivedAt: Date.now(),
    meta: {
      loading: false
    }
  }
}
```

- 4)	In reducer.js add a reducer to modify store tree:
```js
// data store from backend
const initDataState = {
  restReturnObject: null
}
function data(state = initDataState, action) {
  switch (action.type) {
    case t.RECEIVE_REST_RETURN_OJBECT:
      return Object.assign({}, state, {
        restReturnObject: action.restReturnObject,
      })
    default:
      return state
  }
}
```

- 5)	In actions.js add a public async action:
```js
export function fetchRestServiceData (requestJson, callback) {
  return (dispatch, getState) => {
    dispatch(requestData('fetchRestServiceData'))
    return request('http://server/services/rest/path', requestJson)
      .then(data => {
        let { restReturnObject } = data
        dispatch(setRestReturnObject(restReturnObject)) // save to store to waiting for container map this store object to props
        callback && callback(null, restReturnObject) // to use in view after action callback immediately
      })
      .catch((err) => {
        console.log('server error', err)
        dispatch(receiveError(err.toString()))
        callback && callback(err.toString())
      })
  }
}
```

- 6)	In XxxContainer.js (or other modules container) map returned object to props if you want keep it in view (router change by browser history will keep redux stote tree)
```js
const mapStateToProps = (state) => ({
  loading: !state.loading.done,
  restReturnObject: state.xxx.data.restReturnObject
})
```

- 7)	Call this action in view after page start:
```js
componentWillMount () {
  let params = {
    requestKey: ''
  }
  this.props.actions.fetchRestServiceData(params, (error, restReturnObject)=> {
    // handle error or restReturnObject
  })
}
```

- 8) Use this rest model in view:
```js
this.props.restReturnObject
```

# 15.	How to call an UI action to set UI model to store tree and shares between pages in browser session
- 1)	In reducer.js, add UI model you want to save to store which may come from view state, such as:
```js
// ui store from view
const initUiState = {
  uiModel: null
}
function ui (state = initUiState, action) {
  switch (action.type) {
    default:
      return state
  }
}
```

- 2)	In actionTypes.js add an action type that describe what you want to modify store tree, module action name must start with ‘Xxx/’ (global action could have not prefix), such as:
```js
export const SET_UI_MODEL = 'xxx/SET_UI_MODEL'
```

- 3)	In actions.js add a public action:
```js
export function setUiModel(uiModel) {
  return {
    type: t.SET_UI_MODEL,
    uiModel,
    receivedAt: Date.now(),
    meta: {
      loading: false
    }
  }
}
```

- 4)	In reducer.js add a reducer to modify store tree:
```js
// ui store from view
const initUiState = {
  uiModel: null
}
function ui (state = initUiState, action) {
  switch (action.type) {
    case t.SET_UI_MODEL:
      return Object.assign({}, state, {
        uiModel: action.uiModel,
      })
    default:
      return state
  }
}
```

- 5)	Call this action in anywhere:
```js
this.props.actions.setUiModel(this.state.model)
```

- 7)	In XxxContainer.js (or other modules container) map UI model object to props if you want use it in any view:
```js
const mapStateToProps = (state) => ({
  loading: !state.loading.done,
  restReturnObject: state.xxx.data.restReturnObject,
  uiModel: state.xxx.ui.uiModel,
})
```

- 8) Use this UI model in view:
```js
this.props.uiModel
```

## 16.	How to use cross module actions and model
- 1)	You can dispatch other module’s actions in container (if other module is not initialized, call its actions will do nothing), such as:
```js
import * as otherActions from '../../Other/modules/actions'

const mapDispatchToProps = (dispatch, props) => {
  return {
    actions: bindActionCreators(actions, dispatch),
    otherActions: bindActionCreators(otherActions, dispatch),
  }
}
```

- 2)	You can also map other module’s model in redux store tree in container (you must check whether other module store tree exists), such as:
```js
const mapStateToProps = (state) => ({
  loading: !state.loading.done,
  myData: state.my.data.myData,
  myUiModel: state.my.ui.myUiModel,
  otherData: state.other? state.other.data.otherData : null,
  otherUiModel: state.other? state.other.ui.otherUiModel : null,
})
```

## 17.	i18n
- 1)	Solution is based on GNU standard, and I choose tools to follow it
- 2)	Tools: grunt, gettext, msgmerge, po2js
- 3)	Please read i18nProcess.txt
- 4)	Current gettex only scan .js file, so if you don’t want gettext scan them then rename them to .jsx

## 18.	How to write a UI component
- 1)	Common components please refer to code in components folder
- 2)	Business components please refer to each module’s components folder
- 3)	Common components must have propTypes, could have defaultProps

## 19.	HTML and CSS rules
- 1)	Recommend to use flex box (add –webkit- if require all phone browser support) because it is a multi-devices and multi-languages html page, but you can choose bootstrap also
- 2)	HTML element semanticization
- 3)	flexible.js is used to set root font size and body font size based on screen size
- 4)	Size based on rem (proportion of root font size)
- 5)	Font size based on body font size, percentage and fixed (px) value are all recommend
- 6)	Because webpack won’t optimize bundle (will be duplicated packed if import other scss file), so do not import other business module’s scss. Please keep scss file and UI component can work alone.

## 20.	Release package nginx config
```nginx
location /app {
  root   /path-to-dist-folder;
  index  /index.html;
  try_files $uri /index.html;
}
```
