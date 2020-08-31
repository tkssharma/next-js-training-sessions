# Part 01

In this tutorial we will setup our [Next.js](https://github.com/zeit/next.js) application and install the necessary dependencies to get starting building a Server Side Rendered React store from scratch with the [moltin](https://moltin.com).


### Setup

You'll want to create a directory for your project and change directory into your newly created project. Throughout this tutorial I have named my project `nextjs-app`.

```bash
mkdir nextjs-app
cd nextjs-app
```

### Install dependencies

Now you're inside the folder, we need to install our dependencies. Next.js allows us to bring our own version of React and React DOM.

We will use [Yarn](https://yarnpkg.com/en/docs/install) and specify the `-E` flag to make sure we're installing the current available package version.

```bash
yarn add -E react react-dom next
```

### Configure scripts

With our dependencies installed, you'll want to open your project inside your code editor and open the `package.json` file.

Inside the `package.json` we are going to add the required `scripts` to `start`, `build` and serve our application in development (`dev`).

I'd recommend adding these above the dependencies list, so they're easier to find when you install additional dependencies later.

```json
"scripts": {
  "dev": "next",
  "build": "next build",
  "start": "next start"
},
```

### Create an index page

Before we invoke the `dev` script, we need to create an index page. Right now we'll output 'hello world' to the screen. This page will later show all our products.

Next.js was built with the convention over configuration approach, so as long as we follow the Next.js conventions, we should get up and running fairly quickly.

Create a directory called `pages`, and inside that folder, create a file called `index.js`. You can use your code editor or your command line to do this.

```bash
mkdir pages
touch pages/index.js
```

Inside of `pages/index.js` we're going to output `Hello world`. You don't need to import React either, Next.js takes care of this for us.

```js
export default () => <h1>Hello world</h1>
```

### Start the development

We're now able to run our project and see `Hello world` in our browser. To do this...

```bash
yarn dev # or npm run dev
```

Next.js will greet you that your application is running at [http://localhost:3000](http://localhost:3000) by default.

```bash
touch next.config.js
```

Inside this file, you will want to place the following code;

```js
module.exports = {
  webpack: config => {
    config.node = {
      fs: 'empty'
    }

    return config
  }
}
```