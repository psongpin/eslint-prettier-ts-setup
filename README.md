## Basic Linting and Formatter Setup on CRA

This repo documents the setup for Typescript, ESLint with Airbnb config, Prettier, Husky, Lint-Staged with React on CRA.

### Create React App

Follow project installation guide for typescript: https://create-react-app.dev/docs/getting-started/#creating-a-typescript-app

### ESLint, Prettier, Typescript

- Run `npm install eslint --save-dev` to install ESLint to local project folder.
- Run `npx eslint --init` or `./node_modules/.bin/eslint --init` to initialize eslint setup.
- During the initialization, it will prompt you to answer some questions essential to the need of the project. Here are the answers that I use for the setup (answers in bold):

  - How would you like to use ESLint? **To check syntax, find problems, and enforce code style**
  - What type of modules does your project use? **JavaScript modules (import/export)**
  - Which framework does your project use? **React**
  - Does your project use TypeScript? **Yes**
  - Where does your code run? **Browser**
  - How would you like to define a style for your project? **Use a popular style guide**
  - Which style guide do you want to follow? **Airbnb (https://github.com/airbnb/javascript)**
  - What format do you want your config file to be in? **JSON**

- After answering the question, It will prompt you to install some missing dependency.

  - Would you like to install them now with npm? **Yes**

- It will generate a `.eslintrc.json` file with some initial configs. I prefer to rename my file with `.eslintrc` as preference.
- Install the following packages as dev dependencies: `npm i prettier eslint-config-prettier eslint-plugin-prettier --save-dev`
- Update `.eslintrc`:
- Create `.prettierrc`:
- Add to `scripts` in package.json

```
"lint": "eslint 'src/**/*.{js,jsx,ts,tsx}'",
"lint:fix": "npm run lint -- --fix",
"format": "prettier --write 'src/**/*.{ts,tsx,css,scss}'"
```

- Update `.tsconfig.json`:

### Husky and Lint-staged

-`npm i husky lint-staged --save-dev`

- Create `.huskyrc`:
- Create `.lintstagedrc`:

### VSCode

- In Visual Studio Code go to View ->Extensions.
- Search for prettier code formatter and ESLint
- Prettier: https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode
- ESLint: https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint
- Restart/Reload if needed.
- In VSCode settings change or add the following:

```
"editor.formatOnSave": true,
"editor.defaultFormatter": "esbenp.prettier-vscode"
```
