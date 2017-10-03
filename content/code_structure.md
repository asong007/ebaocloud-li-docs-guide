---
title: Code Structure
order: 5
description: The code structure
date: 2017-07-15
updated: 2017-07-15
comments:	true
---

### Root /
When you finish the [enviroement setup](./setup.html), you should see below code in your project fold.
```bash
/
├── .editorconfig
├── .eslintignore
├── .eslintrc
├── .gitignore
├── .travis.yml
├── Gruntfile.js                                # Grunt tasks config file
├── LICENSE                                     # LICENSE file
├── README.md                                   # read me file
├── build/                                      # All build-related code
├── doc/                                        # All related documents
├── gettext0.19.8.1-iconv1.14-shared-64.exe     # gettext and iconv binaries for Windows.
├── lib/                                        # 3rd party js libary fold
├── node_modules                                # Node Modules fold. Packages are dropped into the here.
├── package-lock.json                           # A lock file is a snapshot of the entire dependency tree and includes all packages and their resolved versions.
├── package.json                                # All npm packages, this file holds various metadata relevant to the project.
├── project.config.js                           # project configuration file
├── public/                                     # Static public assets (not imported anywhere in source code)
├── server/                                     # Express application that provides webpack middleware
├── src/                                        # Source code folder,
├── tests/                                      # test case fold
└── translations/                               # local translations files
```

### src/
In the src fold list all source code files.
```sh
src/
├── codetable/
├── common/                         # common utils
│   ├── actions.js                  # common loading handle actions
│   ├── history.js                  # overwritten browser history with base name ‘app’
│   ├── request.js                  # simplify es6 fetch
│   ├── resource.js                 # static resource utils
│   ├── share.js                    # overwritten share button behavior by different use case
│   └── utils.js                    # util functions
├── companies/                      # company components for special inputs and flow during proposal, company code is folder name, CompanyComponents should be customized by each insurer
│   ├── HEXIE_HEALTH
│   ├── huax
│   └── index.js
├── components/
│   ├── App.js
│   ├── Dialog
│   ├── Form
│   ├── Header
│   ├── Modal
│   ├── NativeImageUpload
│   ├── NavTab
│   ├── Pikcer
│   ├── Popup
│   ├── Question
│   ├── SearchBar
│   ├── Signature
│   ├── Steps
│   └── Tag
├── config.js                         # config (should also be packed into bundle)
├── i18n/                             # localized strings files
├── index.html                        # webpack entry point of html template
├── layouts/                          # page layout, can add page in and out animation
├── main.js                           # webpack entry point of js
├── normalize.js                      #
├── routes/                           # web app page router and business module
│   ├── BrowserHistory
│   ├── Clause
│   ├── CompanyIntro
│   ├── DetailDescription
│   ├── Disease
│   ├── Home
│   ├── PersonalPlan
│   ├── Plan
│   ├── ProductDetails
│   ├── ProductList
│   ├── Quote
│   └── index.js
├── store/                            # Redux-specific pieces
└── styles/                           # Application-wide styles (generally settings)
```

### route/
Routes child folder code structure. There many routes which controlled by Redux. Please refer to [Route](./routes.html). In each route, it contains below code:
```sh
route/abc/
      ├── assets/                     # 
      ├── components/                 # react UI components view or page
      ├── containers/                 # redux container that connect view and store
      ├── index.js                    # dynamic router entry point
      └── modules/                    # redux modues
```
