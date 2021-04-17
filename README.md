# vuecrud

 This project aims to maintain basics of Vue.js project construction through CRUD functions via Google Firebase.

## How to setup a Vue.js project via firebase
``` bash
# Create Firebase project
Create db in test mode > create collection(db)
```
``` bash
# Create Vue Project
npm install -g vue-cli
```
``` bash
# Go to the project folder with cd and
vue init webpack appName > cd to appName and npm install
```
``` bash
# Install firebase
npm install firebase --save
```

``` bash
# Apply firebase settings to the project
create firebaseConfig.js which contains  in components folder

export default {
apikeyvs. information in firebase
}

create firebaseInit.js which contains

import firebase from 'firebase/app'
import  'firebase/firestore'
import firebaseConfig from './firebaseConfig'

const firebaseApp = firebase.initializeApp(firebaseConfig)
export default firebaseApp.firestore()
```


## Build Setup
``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
