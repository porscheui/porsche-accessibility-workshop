# Accessibility Workshop for Developers

Demo application for an accessibility workshop.
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

## Workshop

### Introduction
This workshop is for **developers** who want to learn how to find and fix the most common accessibility issues. 
It is based both, on findings from recent accessibility audits and best practices in general, but it doesn't claim to cover a complete list of possible accessibility issues a page can have.
There are two static HTML pages:
- **worst practice example** --> `./public/index.html`
- **best practice example** --> `./public/index-accessible.html`)

Open these two pages in your browser and compare them visually and by behaviour (e.g. try to navigate by a keyboard)

**Hint:** The example pages are one-pagers and are not 

#### Basic knowledge preferable
- Some decent understanding on how to use [Porsche Design System Components](https://designsystem.porsche.com/)
- Knowledge about **HTML/CSS**

### 

### 1. Automatic testing
Automatic accessibility testing can give you fast results of possible accessibility issues. 
Be aware that the results need to be checked manually  and do **only cover up to 20% of possible issues**.

#### Get 1st impressions
1. Start application in dev mode with `yarn start:watch`.
1. Open Chrome and go to **http://localhost:5000/**.
1. Switch to **"axe DevTools"** tab in Chrome Dev Tools (be sure you have installed the extension!).
1. Click **"Scan all of my page"**.
1. Inspect all the issues, try to understand what's the meaning and become familiar with the testing tool.

#### Start fixing issues found by axe DevTools
1. Be sure your local server is running. If not, start application with `yarn start:watch`.
1. Open up following HTML file in your preferred editor: `./public/index.html`.
1. Start fixing issues found by the DevTools in following order: critical, serious, moderate, minor.
1. Retest again, and you should end up with only 3 issues which must be tested/reviewed manual.

### 2. Manual testing
As already mentioned, an automatic accessibility test can only cover up to 20% of possible issues. 
So we have to make our hands dirty and dive into the HTML file to fix and optimize our code base.

#### The Accessibility Checklist
1. Open up the accessibility guidelines on [Porsche Design System Accessibility Workflow](https://designsystem.porsche.com/latest/#/accessibility/workflow) and go to section **"Audit"** where you find an accessibility checklist which you can use to find basic issues.
1. Some of the "top 5" potential issues should have been already fixed (like alt-text and color contrast issues), so we will skip the other ones (for now) and head over to the next section.
1. Go through the other sections of the checklist and fix/optimize as many issues as possible.
1. Last but not least, fix all issues regarding keyboard accessibility (mostly focus state and order).
1. Little help: There are around **50 issues** in total which can be fixed/optimized 💪!

### 3. Compare
1. If you think that you've found and fixed all possible errors, open up Chrome and go to **http://localhost:5000/index-accessible.html**.
1. Try to discover the visual and technical differences with the testing tools and manually by yourself.
1. Open the best practice example **index-accessible.html** in your preferred editor and compare the code with the fixes you made.
1. Your fixes and improvements should result in a **Lighthouse Score of 100** and with only **3 issues left in axe DevTools** which couldn't assessed automatically and do require manually review.

### 4. Learn and discuss
Due to the fact that there are many possible solutions how to fix accessibility issues, it might be worth to push your state to Github and discuss it afterwards with others. 
If you have followed the naming convention while creating a new branch, your application will also be deployed to Github Pages and can be accessed with the following url:  
- https://porscheui.github.io/porsche-accessibility-workshop/workshop/your-name/
- https://porscheui.github.io/porsche-accessibility-workshop/workshop/your-name/index-accessible.html
