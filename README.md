# Adopt-Me-with-React.
Frontendmasters Workshop

# Prettier & Eslint Config

**Extensions**: install eslint and prettier

#### Prettier:



- [x] require config 

- [x] format on save  

`npm init -y`

`npm install -D prettier  eslint  eslint-config-prettier babel-eslint  eslint-plugin-import  eslint-plugin-jsx-a11y  eslint-plugin-react  eslint-plugin-react-hooks`

````{
  "extends": [
    "eslint:recommended",
    "plugin:import/errors",
    "plugin:react/recommended",
    "plugin:jsx-a11y/recommended",
    "prettier"
  ],
  // 0: turn off, 1:warn, 2:error
  "rules": {
    "react/prop-types": 0,
    "no-console": 1,
    "react-hooks/rules-of-hooks": 2,
    "react-hooks/exhaustive-deps": 1
  },
  "plugins": ["react", "import", "jsx-a11y", "react-hooks"],
  //"parser": "babel-eslint",
  "parserOptions": {
    "ecmaVersion": 2018,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "es6": true,
    "browser": true,
    "node": true
  },
  "settings": {
    "react": {
      "version": "detect" //figure it out which React version
    }
  }
}
````

# Babel Config

`npm install -D babel-eslint @babel/core @babel/preset-env @babel/plugin-proposal-class-properties @babel/preset-react`

**"@babel/preset-react"** : Transpile React, understanding JSX

**"@babel/preset-env"** : This will transpile code for the environment that you specify (Chrome, Safari, Firefox) , transpile all the JS so it works on in the Browsers

**"@babel/plugin-proposal-class-properties"** : state = { loading: true };

### .eslintrc

````
{
   "parser": "babel-eslint",
}
````
### .babelrc
````
{
  "presets": ["@babel/preset-react", "@babel/preset-env"],
  "plugins": ["@babel/plugin-proposal-class-properties"]
}
````

## Equivalent

````
constructor(props){
  super(props)
  this.state={loading:true}
}
````
````
state = { loading: true };
````

# Scripts

`npm install -D parcel-bundler`

`npm install react react-dom`

`npm install @reach/router`

`npm install -D cross-env`  Now any time you run this npm run **dev:mock** instead of npm run dev you'll get mock data and not hit the API. This will work offline and if the API is down or taking too long.

````
"scripts": {
    "dev": "parcel src/index.html",
    "dev:mock": "cross-env PET_MOCK=mock npm run dev",
    "format": "prettier --write \"src/**/*.{js,jsx}\"",
    "lint": "eslint \"src/**/*.{js,jsx}\" --quiet",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
````
