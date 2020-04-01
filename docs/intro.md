# Introduction
___

### Intro

" We consider the relentless search
for the best tool to be an optimization fallacy"
  - Daniel Vassallo & Josh Pschorr
  - [The Good Parts of AWS](https://gumroad.com/l/aws-good-parts)



### Intro - It's hard to ramp up a modern web application.

### Boilerplate and Scaffolding 
* Independent & reusable components
* Worldclass DX
  * HMR, 
  * Intelisense
  * Scaffolding Tools
  * ES6 and above
  * Intuitive Achitecture
  * Low Signal to noise ratio
* A consistant baseline
  * Proven to work at scale
  * Reduce complexity
  * Enforced best practices

### Examples
- Todo MVC w/ Admin
- Documentation
- Tutorial


### Technology Stack
  * Create React App
  * Typescript
  * GraphQL (Apollo)
  * Ant Design
  * MobX
  * ESLint
  * Jest
  * Storybook
  * Formik
  * Git
  * JSDoc
  * AWS S3

### Features
* Modern React Application 
* Scalable to Infinity
* Functional & Modular
* scaffolding for rapid application development
* Lazy Loading for pages, models, services, view comoponents and styles
* Modern development env (HMR)
* Industy Standards & Best Practices
* \>= ES6
* Dead simple Routing

**Routes.tsx**
```jsx
// An Example Route Config
// Conceptually similar to Routes.rb
// But, actually completely different IRL
import LayoutA from './layouts/LayoutA';
import LayoutB from './layouts/LayoutB';

// In a production env you would want to lazy load
// these, but this is just an example so chill
import HomePage from './pages/Home';
import AboutPage from './pages/About'


export default [
  {
    name: "Home"
    page: HomePage,
    layout: LayoutA,
    url: "/",
    exact: true // React-Router config
  },
  {
    name: "About", // Self-Documenting code
    page: AboutPage,
    layout: LayoutB,
    url: "/about"
  }
  // ANT-MAN:TOTEM - USED FOR SCAFFOLDING
  // USELESS IN THIS EXAMPLE THO
];

```



## Philosophy


### The Default Heuristic

The following is an excerpt from "The Good Parts of AWS" written
by Daniel Vassallo & Josh Pschorr:


> Searching for the optimal option is almost always
expensive. Any belief that we can easily discover the best
option by exhaustively testing each one is delusional. To
make matters worse, we developers tend to enjoy
tinkering with new technology and figuring out how
things work, and this only amplifies the vicious cycle of
such a pursuit.

> Instead of searching for the best option, we recommend a
technique we call the default heuristic. The premise of
this heuristic is that when the cost of acquiring new
information is high and the consequence of deviating
from a default choice is low, sticking with the default will
likely be the optimal choice.

> But what should your default choice be? A default choice
is any option that gives you very high confidence that it
will work. Most of the time, it is something you’ve used
before. Something you understand well. Something that
has proven itself to be a reliable way for getting things
done in the space you’re operating in.

> Your default choice doesn’t have to be the theoretical
best choice. It doesn’t have to be the most efficient. Or
the latest and greatest. Your default choice simply needs
to be a reliable option to get you to your ultimate
desirable outcome. Your default choice should be very
unlikely to fail you; you have to be confident that it’s a
very safe bet. In fact, that’s the only requirement.
With this heuristic, you start making all your choices
based on your defaults. You would only deviate from your
defaults if you realize you absolutely have to.

> Daniel Vassallo & Josh Pschorr

> <a href="https://gumroad.com/l/aws-good-parts">The Good Parts of AWS</a>
> 

<hr />

* referring to server archetecture, but makes sense for picking front-end frameworks


  * Decomposition creates apps that are easier to manage and work with (preformed, maintained,
  and tested in isolation
  * Scaffolding & boilerplate makes you faster as a developer
    * shifts focus where it should be (business logic)
* Designed to reduce cognitive load of Modern App Dev
  * Architecture and tooling decisions 

    **An Incomplete List of Config Files for a Modern Web Client**

    1. package.json
    2. tsconfig.json
    3. .babelrc
    4. nodemon.json
    5. .eslintrc.json
    6. .eslintignore
    7. .git
    8. .gitconfig 
    9. .gitignore
    10. .gulpfile.esm.js
    11. .env
    12. babel.config.json
    13. template.json
    14. webpack.config.js
    15. webpackDevServer.config.js
    16. jest.config.js
    17. nginx.conf
    18. Docker config
    19. .prettierrc.js 
    20. .vscode/settings.json
    21. lerna.json
    22. AWS.Config

  * Self documenting examples of how to extend the codebase
  * Super Opinionated Codebase
    * Favour Small modules
    * Functional code base encapsalted in classes
  * Modular code w/ HOC - ability to disagree
  * K.I.S.S.


### Choose your adventure!
  * Wanna just dive in - check out the Quick Start
  * Want to deeply understand the application archetecture and design decisions, build your own here (tutorial)

