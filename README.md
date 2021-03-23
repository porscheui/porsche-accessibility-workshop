# Accessibility Workshop for Developers
Demo application of the accessibility workshop for developers.
See also the [deployed project](https://porscheui.github.io/porsche-accessibility-workshop).

## Build status
[![Actions Status](https://github.com/porscheui/porsche-accessibility-workshop/workflows/Porsche%20Accessibility%20Workshop/badge.svg)](https://github.com/porscheui/porsche-accessibility-workshop/actions)

---

## Prerequisites
- [Node.js](https://nodejs.org)
- [Yarn](https://yarnpkg.com)
- [Chrome Browser](https://www.google.com/intl/de_de/chrome/)  
- [AXE DevTools Chrome Extension](https://chrome.google.com/webstore/detail/axe-web-accessibility-tes/lhdoppojpmngadmnindnejefpokejbdd)
- [Access to NPM repository to install Porsche Design System Components](https://designsystem.porsche.com/latest/#/start-coding/introduction)

## Getting started

### Setup
1. Clone [porsche-accessibility-workshop repository](https://github.com/porscheui/porsche-accessibility-workshop) 
1. Switch to **project root directory**
1. Execute command `npm login --registry=https://porscheui.jfrog.io/porscheui/api/npm/npm/`
1. Enter username, password (Artifactory API Key, not Artifactory password!) and e-mail address when asked in terminal

### Install
Run `yarn`

### Start (in watch mode)
Run `yarn start:watch`

--- 

## Introduction
This workshop is for **developers** who want to learn how to find and fix the most common accessibility issues. 
It is based both, on findings from recent accessibility audits and best practices in general, but it doesn't claim to cover a complete list of possible accessibility issues an application can have.

**Hint:** The example pages are static one-pagers, provided only with fake content and do not claim themselves to win design awards.

### Basic knowledge preferable
- Some decent understanding on how to use [Porsche Design System Components](https://designsystem.porsche.com/)
- Knowledge about **HTML/SCSS**

### App structure
There are two static HTML pages. One is the **"bad practice"** example with many baked in accessibility issues you should find and fix, the other ist the **"best practice"** example which is kind of a clone and aims to be accessible.
Styling is provided through a main and component based SCSS files.

#### HTML
- **worst practice example** --> `./public/index.html`
- **best practice example** --> `./public/index-accessible.html`

#### CSS
- **main scss** --> `./src/index.scss`
- **component specific scss** --> `./src/components/{component-name}.scss`

## Workshop
This workshop should teach you how to find and fix most common accessibility issues on an already developed and deployed application. 
Try to find and fix issues only by the help of the tools, guidelines and your own research. Some issues can only be fixed by adapting the CSS files of the component.

**Hint:** If you get stuck, you can always have a sneak preview of the accessibility optimized result page `./public/index-accessible.html` where you can find the optimized version with some linked explanations. 
For CSS only improvements, you can have a look into the corresponding SCSS files where the special styling improvements were made.

### 1. Automatic testing
Automatic accessibility testing can give you fast results of possible accessibility issues. 
Be aware that the results need to be checked manually and do only **cover up to 50% of possible issues**.

#### Warmup: get 1st impressions
1. Create new branch `workshop/your-name` from `master` and be sure that the new branch is your **HEAD branch**
1. Start application in dev mode with `yarn start:watch`.
1. Open the two example pages in Chrome browser on **http://localhost:5000/index.html** and **http://localhost:5000/index-accessible.html**, compare them visually and by behaviour (e.g. try to navigate by a keyboard) and explore differences.

#### Initial accessibility scan with axe DevTools
1. Switch to **http://localhost:5000/index.html**, open Chrome DevTools and navigate to **"axe DevTools"** (be sure you have installed the extension!).
1. Click **"Scan all of my page"**.
1. **Inspect** all the issues, try to understand what's the meaning and [get familiar with the axe testing tool](https://www.youtube.com/watch?v=dyU9yrRJ5Eg).

#### Start fixing issues found by axe DevTools
1. Open up following HTML file in your preferred editor: `./public/index.html`.
1. Start fixing issues found by **axe DevTools** in following order: critical, serious, moderate, minor.
1. Save your fixes, retest again, and you should end up with only 3 issues which must be tested/reviewed manual. 

**Hint:** Some errors occur of a poor implementation of the SPLIDE Carousel plugin. They can be fixed by changing some of the [JS properties of the SPLIDE plugin](https://splidejs.com/options/).
Be aware that if you are using 3rd party tools and plugins in your application, they also have to be accessibility compliant!

### 2. Manual testing
As already mentioned, an automatic accessibility test can only cover up to 50% of possible issues. Therefore, we have to inspect each element on the page individually. 
To help you get through of the most important issues, we created some guidance in form of an accessibility checklist:

#### The Accessibility Checklist
1. Open up the accessibility workflow on [Porsche Design System Accessibility Workflow](https://designsystem.porsche.com/latest/#/accessibility/workflow) and go to section **"Audit"** where you find an accessibility checklist which you can use to find most common issues.
1. Some of the issues should already have been fixed (e.g. missing alt-text and color contrast issues), and you can "check" them as solved.
1. Go through all sections of the checklist and fix/optimize as many issues as possible.
1. Little help: There are around **50 issues** in total which can be fixed/optimized 💪!

### 3. Compare
1. If you think that you've found and fixed all possible issues, open up Chrome and go to **http://localhost:5000/index-accessible.html**.
1. Try to discover the visual and technical differences with the testing tools and manually by yourself.
1. Open the best practice example **index-accessible.html** in your preferred editor and compare the code with the fixes you made.
1. Your fixes and improvements should result with only **3 issues left in axe DevTools** which couldn't assessed automatically and do require manually review.

### 4. Learn and discuss
Due to the fact that there are many possible solutions how to fix accessibility issues, it might be worth to push your state to **Github** and discuss it afterwards with others. 
**Hint:**: You need access to the Porsche GitHub organization to have the rights to push to the repository!

If you have followed the naming convention while creating a new branch, your application will also be deployed to Github Pages and can be accessed with the following url:  
- https://porscheui.github.io/porsche-accessibility-workshop/workshop/your-name/
- https://porscheui.github.io/porsche-accessibility-workshop/workshop/your-name/index-accessible.html
