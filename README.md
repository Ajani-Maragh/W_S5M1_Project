# Sprint 5 Module 1 Project

## Introduction

Welcome to Module 1 Project! In this project, you will practice using "vanilla" JavaScript to manipulate the DOM, without any frameworks. Your goal is to build some widgets on a web-page, using only JavaScript.

To successfully complete this project, you will need the following technical skills:

1. **Selecting elements** and groups of elements from the DOM.
1. **Creating new elements** and attaching them to the DOM.
1. **Looping** over arrays and lists of DOM elements.
1. **Generating pseudo-random numbers** using the Math object.
1. **Using data** and template literals to build text content for elements in the DOM.
1. **Manipulating attributes** on elements.
1. **Using setInterval** to schedule repeated actions.

In addition to these technical skills, the following soft skills will greatly impact your performance:

1. Attention to detail. Make sure there isn't a single character out of place!
1. Perseverance. Keep trying until you figure it out!
1. Patience. Make sure to read the entire README for important information.

## Instructions

You have been given a take-home coding assessment as part of the hiring process for a Web Developer position. Your task is to build some widgets on a web-page, using only JavaScript.

To help you complete the task, two of your future team-members will provide you with instructions and advice. You can find a [detailed mock](https://bloominstituteoftechnology.github.io/W_U2_S5_module_project/) showing the desired end result.

Make sure to carefully read and follow their instructions. Good luck!

### 💾 DevOps Engineer

**Below, a DevOps Engineer will help you set up your local environment and launch the project:**

This is a **full-stack web application** that comprises both back-end and front-end components. If deployed to production, the back-end part would run in the cloud (think Amazon Web Services or Azure), while the front-end would execute inside the user's web browser (like Chrome for Android, or Firefox for desktop).

As a front-end engineer, your focus is mainly on the files that load **on the user's device**. In this particular case, these files live inside the `frontent` folder. The `backend` folder contains a web server built in Node, but the project as a whole is managed as a Node application. As such, it contains a `package.json` file at the root, containing some meta-information like name and version, and a few useful scripts developers can use as they work on the app, like "npm test".

1. You will **clone this repository** to your computer, which will allow you to run the software locally for development and testing purposes.

1. You will navigate your terminal to the project folder **and execute `npm install`**. This will install the libraries declared inside `package.json`. Some of these packages are needed for the back-end to do its job of serving front-end assets. Other libs help with things like testing and linting your code.

1. After successful installation you will run, in separate terminals, two of the scripts found inside `package.json`. To do this, **execute `npm start` in your first terminal, and `npm test` in your second**. On successful start, you will load the app in Chrome by **navigating the browser to `http://localhost:3003`**. The term "localhost" means "your machine", and the number is called a port, allowing multiple web servers to run on the same computer, with one server per port.

1. If you haven't already, install the [Eslint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) for VSCode. It will highlight syntax errors and problems right inside your editor, which saves tons of time.

### 🥷 Lead Developer

**Below, your Team Lead will discuss the tasks you need to complete.**

Hey! Let's make sure you're up to speed with your **action items so far**.

- [x] The app is installed on your machine, with both `start` and `test` scripts running in terminals.
- [x] You studied the [mock](https://bloominstituteoftechnology.github.io/W_U2_S5_module_project/), and saw it loading different content at every reload.
- [x] You loaded your app in `http://localhost:3003`.

Awesome! As you complete your tasks, tests will start passing in the terminal. **Do not stop until all tests are in the green!**

If you look inside the `frontend` folder you will notice it contains, among other assets, two scripts: `data.js` and `index.js`. If you inspect the head element of the `index.html` document, you will find both scripts loading there.

One page can load many scripts, and whatever variables exist at the top-level of each script are accessible by any scripts executing later.

This is why we are including `data.js` first: we want the data it contains available to the `index.js` script. This is how JavaScript programs were traditionally partitioned and loaded on web-sites.

**With all that out of the day, let's discuss `index.js` and the tasks you need to complete inside that script. You are not allowed to modify any other files.**

Have fun, and reach out to Staff if you get too stuck!

#### 👉 TASK 1 - Add a "widget" class name to widgets so CSS kicks in

<details>
  <summary>Click to read</summary>

  ---

Inside the section element of the HTML there are four divs. Add a class name of "widget" to all of them. Do not modify the HTML. Use JavaScript!

You will know your code is working correctly because some CSS will kick in for the widgets, and you will also see a passing test inside the terminal executing your tests. The end result in the DOM should look like the following:

```html
<section>
  <div class="quoteoftheday widget">
    <h3>Quote of the Day</h3>
  </div>
  <div class="corporatespeak widget">
    <h3>Corporate Speak</h3>
  </div>
  <div class="countdown widget">
    <h3>Countdown</h3>
  </div>
  <div class="friends widget">
    <h3>Friends</h3>
  </div>
</section>
```

  ---

</details>

#### 👉 TASK 2 - Build a "Quote of the Day" widget

<details>
  <summary>Click to read</summary>

  ---

Let's start by console logging the variable `quotes`. If you do this inside `index.js`, you should see an array of quote objects printing to the console. Even though this variable is not declared anywhere inside the file, it is _defined_ because the `data.js` script loaded it into the global space shared by all scripts.

(You can also evaluate top-level variables by just entering them into the console and hitting Enter.)

Now that we have determined we have access to an array of quotes, you will use `Math.random` to generate a random index **between 0 and 9** (you can Google, or ask ChatGPT how). You will use this random index to grab one of the quotes in the quotes array.

Use the random quote you selected to construct the following piece of DOM:

```html
<!-- the actual text will change at every reload, depending on the quote -->
<div class="quoteoftheday widget">
  <h3>Quote of the Day</h3>
  <div>Optimism is an occupational hazard of programming: feedback is the treatment.</div>
  <div>Kent Beck in 2003</div>
</div>
```

Some of the quotes have a `null` date because it is unknown. In such cases, the div containing the author should be in the following format:

```html
<!-- the name will change depending on the quote -->
<div>John Romero in an unknown date</div>
```

  ---

</details>

#### 👉 TASK 3 - Build a "Corporate Speak" widget

<details>
  <summary>Click to read</summary>

  ---

Using the `adverbs`, `nouns` and `verbs` in `data.js`, construct DOM in the following format:

```html
<div class="corporatespeak widget">
  <h3>Corporate Speak</h3>
  <p>
    We need to <!-- random verb --> our <!-- random noun --> <!-- random adverb -->
    in order to <!-- random verb --> our <!-- random noun --> <!-- random adverb -->.
  </p>
</div>
```

  ---

</details>

#### 👉 TASK 4 - Build a "Countdown" widget

<details>
  <summary>Click to read</summary>

  ---

- This widget on page load displays "T-minus 5...".
- 1000 milliseconds later, it should display  "T-minus 4..."
- 1000 milliseconds later, it should display  "T-minus 3..."
- 1000 milliseconds later, it should display  "T-minus 2..."
- 1000 milliseconds later, it should display  "T-minus 1..."
- 1000 milliseconds later, it should display  "Liftoff! 🚀"

You will need `setInterval` and optionally `clearInterval` (research this!). The DOM after 3000 milliseconds should look like so:

```html
<div class="countdown widget">
  <h3>Countdown</h3>
  <p>T-minus 2...</p>
</div>
```

  ---

</details>

#### 👉 TASK 5 - Build a "Friends" widget

<details>
  <summary>Click to read</summary>

  ---

Select a random person from the `people` array in `data.js`, using `Math.random` for this.

Each person has, among other attributes, a `friends` array containing the IDs of some buddies, which are also contained inside the `people` array.

Use the random person to construct DOM in the following format:

```html
<div class="friends widget">
  <h3>Friends</h3>
  <p>Michael Chen was born in 1995 and is friends with Carlos Garcia, Mohammed Ali and Jason Wong.</p>
</div>
```

Note how the string is formatted, taking careful note of punctuation and proper placement of the "and" before the last friend.

The friends mentioned in the p tag come from the `friends` property of the randomly selected person.

In the example above, Carlos Garcia, Mohammed Ali and Jason Wong are the people who correspond to the IDs inside Michael Chen's `friends` array.

If the person is unlucky enough not to have any friends inside their `friends` property, the paragraph renders to the DOM like so:

```html
<p>Luis Gonzalez was born in 1990 and has no friends.</p>
```

  ---

</details>

#### 👉 Task 6

<details>
  <summary>Click to read</summary>

  ---

We need to be able to tab between widgets using the Tab key, which helps make the site more accessible.

In order to do this, select the first widget from the DOM and add give it a `tabindex` attribute of "1".

The second one should have a `tabindex` of "2" and so on. Here is what the Countdown widget would look like as an example:

```html
<div class="countdown widget" tabindex="3">
  <h3>Countdown</h3>
  <p>Liftoff! 🚀</p>
</div>
```

  ---

</details>

  ---

</details>

## FAQ

<details>
  <summary>I am getting errors when I run npm install or npm start. What is going on?</summary>

This project requires Node correctly installed on your computer in order to work. Your learning materials should have covered installation of Node. Sometimes Node can be installed but mis-configured. You can try executing `npm run fixit` (check `package.json` to see what this does), but if Node errors are recurrent, it indicates something is wrong with your machine or configuration, in which case you should request assistance from Staff.

</details>

<details>
  <summary>Do I need to install libraries or add scripts to the HTML?</summary>

No. Everything you need should be installed already, including Axios.

</details>

<details>
  <summary>Why am I not allowed to edit the CSS file?</summary>

The CSS is the domain of a different team, and in this particular project we're not supposed to touch it. Do not use inline styles to get around this limitation! It will only make the CSS team angry. And believe us, you want CSS specialists happy because they can write CSS twenty times faster than you.

</details>

<details>
  <summary>Why am I not allowed to edit the HTML file?</summary>

This particular part of the product is a Single Page Application, so the HTML is mostly empty and the page is generated automatically using JavaScript and raw data. We would not want to manually edit HTML files in a website that changed all the time! It would be untenable.

</details>

<details>
  <summary>My page does not work! How do I debug it?</summary>

Save your changes, and reload the site in Chrome. If you have a syntax problem in your code, the app will print error messages in the Console. Focus on the first message. Place console logs right before the crash site (errors usually inform of the line number where the problem is originating) and see if your variables contain the data you think they do. If there are no errors but the page is not doing what it's supposed to, the debugging technique is similar: put console logs to ensure that the code you are working on is actually executing, and to check that all variables in the area hold the correct data.

</details>

<details>
  <summary>How do I run tests against my code?</summary>

Execute `npm test` in your terminal. If a particular test is giving you grief, don't jump straight to the code to try and fix it. Go to Chrome first, and make sure you can replicate the problem there. A problem we can reliably replicate is a problem mostly fixed.

</details>

<details>
  <summary>I believe my code is correct and the test is wrong. What do I do?</summary>

On occasion the test runner will get stuck. Use CTRL-C to kill the tests, and then `npm test` to launch them again. Try to reproduce the problem the test is complaining about by interacting with the site in Chrome, and do not code "to make the test happy". Code so that **your app does exactly what the mock does**. The tests are there for confirmation. Although it's possible that a particular test be flawed, statistically it's more likely that the bug is in your own code. If the problem persists, please request assistance from Staff.

</details>

<details>
  <summary>The output of the test script is just too overwhelming! What can I do?</summary>

If you need to disable all tests except the one you are focusing on, edit the `mvp.test.js` file and, as an example, change `test('👉 focus on this', () => { etc })` to be `test.only('👉 focus on this', () => { etc })`. (Note the "only".)

</details>

<details>
  <summary>I messed up and want to start over! How do I do that?</summary>

**Do NOT delete your repository from GitHub!** Instead, commit _frequently_ as you work. Make a commit whenever you achieve _anything_ and the app isn't crashing in Chrome. This in practice creates restore points you can use should you wreak havoc with your app. If you find yourself in a mess, use `git reset --hard` to simply discard all changes to your code since your last commit. If you are dead-set on restarting the challenge from scratch, you can do this with Git as well, but it is advised that you request assistance from Staff.

</details>

<details>
  <summary>Why are there so many files in this project?</summary>

Although a small, "old-fashioned" website might be made of just HTML, CSS and JS files, these days we mostly manage projects with Node and its package manager, NPM. Node apps typically have a `package.json` file and several other configuration files placed at the root of the project. This project also includes automated tests and a web server, which adds a little bit of extra complexity and files.

</details>

<details>
  <summary>Is this how web projects are normally organized?</summary>

Web projects can be organized in a million ways, there aren't many standards. Some developers like the freedom, while others prefer to use opinionated frameworks, which can do a lot of magic but prescribe that folders and files be structured and named just so.

</details>

<details>
  <summary>Why is my code inside index.js wrapped in an async function called "sprintChallenge5"?</summary>

This way we can easily import your code as a single function in the `mvp.test.js` test suite. The export syntax is at the bottom of `index.js`. The function declaration is prefixed by the `async` keyword to allow you to use `await` inside it.

</details>

<details>
  <summary>What are the package.json and package-lock.json files?</summary>

The `package.json` file contains meta-information about the project like its version number, scripts that the developer can execute, and a list of the dependencies that are downloaded when you execute `npm install`. There can be some wiggle room to allow newer versions of the dependencies to be installed, so the `package-lock.json` file, when present, makes sure the exact same versions of everything are used every time the project is installed from scratch.

</details>

<details>
  <summary>What is the .eslintrc.js file?</summary>

This file works in combination with the Eslint extension for VSCode to highlight syntax errors and problems in your code. By editing this file you can customize your linting rules.

</details>

<details>
  <summary>What is Jest?</summary>

Jest is a framework that allows you to write tests and execute them, to alert you very quickly of problems with the code. Jest can do in seconds what an entire Quality Assurance team would take hours or even days. In the context of the Sprint Challenge, Jest is used to check your code against specification and give you a grade (% of tests passing).

</details>
