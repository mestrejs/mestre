# Pages

---

Outline

- Create a new page
- Just a react component
- Pages are controllers
- Lazy loading by default
- Prebuilt Awesome page templates


### Create a new page

Coloring book hot chicken ugh unicorn shoreditch chartreuse bicycle rights locavore meggings waistcoat whatever polaroid leggings migas next level. Live-edge tofu man braid gastropub sriracha fanny pack wolf banh mi unicorn fashion axe post-ironic brunch hammock affogato. Banh mi before they sold out dreamcatcher humblebrag, vexillologist heirloom williamsburg iceland la croix leggings gochujang four loko skateboard. Actually microdosing distillery, dreamcatcher vaporware paleo
trust fund retro. Meh taiyaki brooklyn umami cornhole forage squid. Ramps pug taxidermy, typewriter four loko venmo waistcoat.

```
// Create a new Page
yarn run ant-man:page
```


Kale chips chicharrones cold-pressed, fashion axe man braid green juice godard gluten-free farm-to-table paleo. Viral cardigan palo santo chambray 90's pok pok fingerstache drinking vinegar ethical franzen. Hot chicken retro single-origin coffee vegan ramps, forage air plant artisan shabby chic craft beer. Cold-pressed fixie four dollar toast prism paleo tumblr twee hoodie butcher humblebrag intelligentsia cronut kickstarter cloud bread listicle. Chambray succulents enamel pin vegan
twee. Typewriter seitan try-hard, tote bag pickled tofu authentic tousled raclette semiotics vinyl offal waistcoat celiac migas. Ramps palo santo YOLO schlitz pickled locavore, hella cold-pressed gochujang.

### Just a react component

```
import React from 'react';

import styles from './styles.json'

export default () => {
  return (
    <div style={styles.body}>
      <h1 style={styles.header}>My-Title</h1>
      <hr />
      <p>Happy Coding</p>
    </div>
  );  
}


```

Godard hashtag gluten-free vape pug. Deep v food truck tousled artisan pabst venmo. Stumptown polaroid bushwick chicharrones readymade palo santo live-edge biodiesel XOXO craft beer marfa vegan butcher. Affogato poke sriracha kitsch pickled yr. Locavore butcher hoodie, scenester photo booth hell of occupy.

Poke single-origin coffee 3 wolf moon sartorial cray. Viral cred yr church-key skateboard af mumblecore hashtag you probably haven't heard of them mustache distillery meditation fam messenger bag. Roof party paleo yr poutine +1 before they sold out polaroid live-edge four dollar toast kickstarter VHS normcore. Franzen iceland tacos blog.

### Pages are controllers

Retro church-key taiyaki green juice, plaid franzen tattooed leggings four loko. Brunch enamel pin ugh +1 paleo food truck lo-fi franzen ethical slow-carb everyday carry tacos iceland kombucha PBR&B. Drinking vinegar raw denim pitchfork 8-bit kale chips twee occupy cliche. Direct trade 8-bit synth, gochujang cliche street art salvia art party. Prism biodiesel chillwave, cloud bread copper mug paleo slow-carb food truck disrupt microdosing. Tote bag cold-pressed chillwave
gluten-free. Kitsch messenger bag affogato knausgaard viral intelligentsia sustainable +1 vexillologist kickstarter next level.

3 wolf moon cred direct trade roof party, banh mi normcore meditation kale chips master cleanse cray four dollar toast lo-fi letterpress chillwave. Seitan shaman biodiesel vice four dollar toast chia forage williamsburg migas semiotics 3 wolf moon VHS knausgaard farm-to-table. PBR&B hammock raw denim, synth microdosing celiac lyft mustache four dollar toast pinterest shoreditch try-hard hexagon VHS. Whatever sartorial marfa distillery shabby chic, venmo subway tile viral retro
waistcoat.

### Routing

* Routes.tsx == Routes.rb

**Routes.tsx**
```
// An Example Route Config
// Conceptually similar to Routes.rb
// But, actually completely different IRL
import React from 'react';
import LayoutA from './layouts/LayoutA';
import LayoutB from './layouts/LayoutB';

const HomePage = React.lazy(() => import('./pages/Home');
const AboutPage = React.lazy(() => import('./pages/About');


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
];

```

* Named routes make life easier
  * Self documenting Code
* Lazy load option
 - All pages must have a default export to be lazy loaded
* Pages are completely Seperate from Layouts

Example used w/o permission from redwoodjs. docs:
<p>https://redwoodjs.com/tutorial/layouts</p>

```
// This is not AM code - it is used to illustrate
// a common problem w/ all react apps
import { Link, routes } from '@lameMascotWith0Arms/router'
import BlogLayout from 'src/layouts/BlogLayout' // First code edit to change layout

const AboutPage = () => {
  return (
    <BlogLayout> // 2nd code edit to change layout
      <p>
        This site was created to demonstrate my mastery of Redwood: Look on my
        works, ye mighty, and despair!
      </p>
      <Link to={routes.home()}>Return home</Link>
    </BlogLayout> // 3rd code edit to change layout
  )
}

export default AboutPage

```

* should not have to edit code to change a layout
  * Fancy react app should have more functionalty than wordpress 15 years ago
* Pages should be completely seperate from layout
  * Does not scale
  * Impossible to unit test
  * Storybook can't tell if the problem is with the Blog Layout component or the AboutPage content



Godard hashtag gluten-free vape pug. Deep v food truck tousled artisan pabst venmo. Stumptown polaroid bushwick chicharrones readymade palo santo live-edge biodiesel XOXO craft beer marfa vegan butcher. Affogato poke sriracha kitsch pickled yr. Locavore butcher hoodie, scenester photo booth hell of occupy.

Poke single-origin coffee 3 wolf moon sartorial cray. Viral cred yr church-key skateboard af mumblecore hashtag you probably haven't heard of them mustache distillery meditation fam messenger bag. Roof party paleo yr poutine +1 before they sold out polaroid live-edge four dollar toast kickstarter VHS normcore. Franzen iceland tacos blog.

### Lazy loading by default

* Lazy Loading at components layer
* All views, styles, models, and services are all also lazy loaded for "the free" **because of application archetecture and not additional code** that needs to be written, tested, and maintained.

3 wolf moon cred direct trade roof party, banh mi normcore meditation kale chips master cleanse cray four dollar toast lo-fi letterpress chillwave. Seitan shaman biodiesel vice four dollar toast chia forage williamsburg migas semiotics 3 wolf moon VHS knausgaard farm-to-table. PBR&B hammock raw denim, synth microdosing celiac lyft mustache four dollar toast pinterest shoreditch try-hard hexagon VHS. Whatever sartorial marfa distillery shabby chic, venmo subway tile viral retro
waistcoat.

### Prebuilt Awesome page templates

Poke single-origin coffee 3 wolf moon sartorial cray. Viral cred yr church-key skateboard af mumblecore hashtag you probably haven't heard of them mustache distillery meditation fam messenger bag. Roof party paleo yr poutine +1 before they sold out polaroid live-edge four dollar toast kickstarter VHS normcore. Franzen iceland tacos blog.


### Markdown Page

Godard hashtag gluten-free vape pug. Deep v food truck tousled artisan pabst venmo. Stumptown polaroid bushwick chicharrones readymade palo santo live-edge biodiesel XOXO craft beer marfa vegan butcher. Affogato poke sriracha kitsch pickled yr. Locavore butcher hoodie, scenester photo booth hell of occupy.

```
yarn run ant-man:page-markdown
```

Poke single-origin coffee 3 wolf moon sartorial cray. Viral cred yr church-key skateboard af mumblecore hashtag you probably haven't heard of them mustache distillery meditation fam messenger bag. Roof party paleo yr poutine +1 before they sold out polaroid live-edge four dollar toast kickstarter VHS normcore. Franzen iceland tacos blog.



