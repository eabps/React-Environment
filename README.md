# React-Environment
This document describes step by step to prepare the environment with [**React**](https://facebook.github.io/react/) and [**Bootstrap**](http://getbootstrap.com/) on SO Ubuntu 16

## Install Dependencies ##

**Node.js** - *Node.js® is a JavaScript runtime built on Chrome's V8 JavaScript engine.*
```sh
$ sudo apt install nodejs && node -v
```

**Yarn** - *Yarn is a package manager for your code. It allows you to use and share code with other developers from around the world.*
```sh
$ sudo apt install yarn && yarn -v
```

**Create-React-App** - *is a lib for easy startup of react projects*
```sh
$ yarn global add create-react-app
```

## Create Project ##
```sh
$ create-react-app project-name
```

**Install Bootstrap 4** - *Bootstrap is an open source toolkit for developing with HTML, CSS, and JS. Quickly prototype your ideas or build your entire app with our Sass variables and mixins, responsive grid system, extensive prebuilt components, and powerful plugins built on jQuery.*
```sh
$ yarn add bootstrap@4
```

## Start Project ##
In directory project, do:
```sh
$ yarn start
```