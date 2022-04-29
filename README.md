# Restaurant Locator React Project

#### [Description](#description) | [Demo](#demo) | [Getting Started](#getting-started) | [Important Notes on APIs](#important-notes-on-apis) | [Requirements](#requirements) | [Bonuses](#bonuses)

---------

## Description:
Over the next few days, you and a partner will be building a React app similar to the demo seen below. This app will firm up your existing knowledge of the React basics (components, JSX, props, event handling, using forms, making API calls, basic hooks) and also utilize newer skills like handling styles using Styled-Components and conditionally-rendering components using React-Router-DOM. Each pair will collaborate on a shared GitHub repository, and each person should contribute roughly half of the code contained within the repository. Although you will be working most closely with your partner, you are both encouraged to work with the rest of the team to discuss strategy, debug issues, review code, etc.

Below you will see a demo of Restaurant Locator app that initially loads Yelp restaurant data for a hardcoded location (Denver), and shows this data both as results list items and as pushpins on a Leaflet map. A user can then click on individual search results to be directed to the restaurant details page, or choose instead to search for restaurants in a new location.

**Note that your app does not need to be a restaurant locator in particular:** you and your partner may choose to make a brewery locator app, a business locator app, a meteorite-landing site map, a crime incident location map, etc etc etc. So long as the app you create meets the [core requirements](#requirements) listed below, feel free to choose an idea that you and your partner are excited to build!

---------

## Demo:

![Restaurant Locator Functionality Demo](restaurant-locator-demo.gif)

[View larger version of demo here](https://watch.screencastify.com/v/c36gH0DHv9bmw6N5AbRX).

---------

## Getting Started:

- [ ] **All work should be done within branches, and code should only be moved to your `main`/`master` branch by way of partner-approved pull requests. As you work, do regular adds/commits to give yourself multiple "save points" just in case something goes wrong.**
- [ ] **Reference the [Git Collaboration Workflow document](https://github.com/scullenBitwise/git-collaboration-workflow) for a list of steps you can use for common Git collaboration tasks!**
- [ ] Take time with your partner to read through the [core requirements](#requirements) below, and to choose an idea to fulfill these requirements.
- [ ] Next, build out simple wireframes for your app using [wireframe.cc](https://wireframe.cc/), [Figma](https://www.figma.com/) or a similar tool. Use these wireframes to determine how to divide your app up into modular components, and to determine how you and your partner can divide up the necessary tasks.
- [ ] Consider using [Trello](http://trello.com) to create a project board to track tasks, priorities, and deadlines, and for visibility into what each partner is working on. [See here](https://trello.com/b/WjhFXOdJ/demo-project-board) for an example of how one might be organized.
- [ ] One partner should create a GitHub repository for your app, and should add the other partner **AND** `scullenBitwise` as collaborators. After the repo is set up, work together to set up [branch protections](https://docs.github.com/en/enterprise-server@3.2/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branches) and determine a game plan for Git branching.
- [ ] Use clear, descriptive, and professional commit messages. (This will make things easier if you ever have to revert to a prior commit, and it looks great to potential employers!)
- [ ] One partner should use create-react-app to generate a new React app for your app: `npx create-react-app project-name-here`. If you need help getting your project linked up to a GitHub repo, just ask! Once this code has been merged into the `main`/`master` branch, the other partner can clone the repo, create a branch, and get started developing!
- [ ] Use the demos provided in class for reference. [Here](https://github.com/scullenBitwise/react-apprenticeship) is a link to the full demo repo.
- [ ] Dig into the React or JavaScript documentation if you get stuck!
- [ ] When you run into a bug or other unexpected behavior, use your debugging tools wisely: read error messages critically, set breakpoints, use `console.log()` and watch variables, use your Google Fu, etc.
- [ ] Challenge yourself to use ES6 syntax whenever possible: arrow functions, destructuring, the spread operator, object property value shorthand, template literals, etc.

---------

## Important Notes on APIs:

### Choosing an API:
Once you and your partner have determined what type of data you would like your locator to search, **immediately** begin researching data APIs. Once you find an API or two that is promising, verify the following:

- Make sure the API is free or has a free tier.
- **tl;dr: Make sure the API allows LOTS of free requests!** APIs often limit the number of requests you can make per day or month. Make sure this number is generous: every time your app reloads it will likely kick off one or more API requests. Remember that if you're making lots of small changes to your app and saving those files, React will hot reload after every save, thus potentially kicking off more API requests with every save. Then remember that if your partner is using the same API key, *they* are also burning through those allotted requests...
  - One somewhat shady way to double your API call capacity is for each parter to register a separate API key, and to write code to randomly choose one of the two API keys everytime a request is made. 
- Make sure the API either required no authentication or simple authentication, else it may not be workable in a front-end app.
- Make sure that it returns data in JSON format.
- Make sure the API has good documentation.
- **Make sure that the API outputs the data your app needs!!!** You can test this initially in Postman or Insomnia. After confirming that the data is returned correctly there, now you must verify you can access the same data through your React app, which is front-end only. **NOTE: Some APIs will work properly through Postman or Insomnia but will not return data to a front-end app like React, due to a lack of CORS permissions on the API server.
- If you run into issues re: the bullet point above, read more about CORS below to determine whether you can find a functional workaround for this project.

### CORS (Cross-Origin Resource Sharing):
Since your app will be front-end-only (with no back-end server), there are some APIs that will not work for you due to a lack of CORS permissions on the API server. Learn more about CORS below, and take a look at a potential workaround:

- [Cross-Origin Resource Sharing (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [What are CORS proxies, and when are they safe?](https://httptoolkit.tech/blog/cors-proxies/)
- [CORS Anywhere](https://cors-anywhere.herokuapp.com/) - this is one of those less than ideal and somewhat risky resources discussed in the article above... but for a simple project like this one with no secure data being transmitted, it's okay in a pinch.

---------

## Requirements:

- [ ] Your app should use `styled-components` for styling rather than scss/regular css.
- [ ] Your app should use `react-router-dom` for conditional rendering of your different "page" elements.
- [ ] Your app should use a React-specific mapping package and load search results onto the map as pushpins. Look into npm packages like [React Leaflet](https://react-leaflet.js.org/), [React Google Maps](https://www.npmjs.com/package/@react-google-maps/api), [Pigeon Maps](https://www.npmjs.com/package/pigeon-maps), [Here Maps React](https://www.npmjs.com/package/here-maps-react-v2), etc. Note that not all mapping APIs are free, so read the fine print!
- [ ] Your app should have a search bar that allows a user to specify a new location to search in. After user search, the map should recenter and show results in the new location.
- [ ] Pull data from your external API using `axios`, `fetch`, or a similar tool. Make sure that your app runs a search for results in the default location upon render, displays search results, and displays pushpins for those results on the map!
- [ ] Your app should have a separate location details "page" that the user can click through to by clicking on a search result (and maybe even by clicking on a map pushpin). This location details component should NOT receive its data via props and should instead use `useEffect()` to pull location details from the API upon initial render. See the [Blog App Demo](https://github.com/scullenBitwise/react-apprenticeship/tree/main/react/11_react-router/3_blog-app) for an example of how to accomplish this.
- [ ] Hide any API keys using a `.env` file. Remember to add the `.env` file to your `.gitignore` so that it is not uploaded to GitHub!
- [ ] Your app should have multiple components. Use props to pass data from parent components into child components to allow customization of the child components. (Sometimes it's easiest to start with one or two big components, and to break code out into smaller, more specific components after the core functionality is in place.)
- [ ] Make your code as DRY (**D**on't **R**epeat **Y**ourself) as possible!

---------

## Bonuses:

- [ ] Allow the user to customize their search by providing additional fields (categories, sort radius, etc)
- [ ] Add filters and/or sort capability to allow the user to customize the search results they see.
- [ ] Have your app auto-detect a user's location on render (if that feature is enabled on the user's end) and use this location to render the initial search results/map pushpins.
- [ ] If your API provides rating data, implement a star display widget (or build the code yourself)!
- [ ] If your API provides photos urls that are pertinent to your app, consider implementing a photo carousel on your result details page.
- [ ] Implement different pushpin/marker styles based on search result categories or whether a search result is current "active."
- [ ] Look into infinite scrolling or pagination, so that only the first `x` results are pulled from the API initially and rendered, and calls for additional results are made as the user clicks to the next page or scrolls to the bottom of the existing search results.
- [ ] Consider implementing autocomplete functionality on your search field. (Use an autocomplete API for this.)
- [ ] Look into implementing driving directions to the selected search result using a directions API.
- [ ] Practice using [Bitwise's official commit message format](https://github.com/Shift3/standards-and-practices/blob/main/standards/commits.md).
- [ ] Deploy your app to GitHub Pages, Netlify, or a similar service and share the url with your team so we can all try it!
- [ ] Write a detailed README.md file using best practices: [README Template](https://gist.github.com/PurpleBooth/109311bb0361f32d87a2)
- [ ] Look into using [Storybook](https://storybook.js.org/docs/react/get-started/introduction) as a tool for building, standardizing, and documenting your React components in isolation.
