# DIY Ant-Man

A deeper introduction into the application architecture, and how all the pieces fit together; and why.

___

_"The best way to learn something new is to implement it yourself."_
~ <a href="https://twitter.com/mpjme">MPJ</a>


Outline

- A "Classical" counter app in react
- Styling our app w/ CSS-in-JSON
- A functional counter app in react w/ hooks
- Pagination w/react-router
- Solving our soaking wet layout conundrum
- Moving our state to it's very own model
- Decoupling state from view w/ MobX 
- Maintaining modularity with HOC's
- A UI Library of our very own
- M-V-C ish?
- Automating the boring stuff with JavaScript
- Which way is wrap-up?

Deep v hammock meh mlkshk cronut, kombucha yr selfies raw denim gentrify bitters iPhone. Locavore jean shorts pinterest edison bulb. Truffaut subway tile thundercats kogi. Lo-fi pabst +1 brooklyn farm-to-table chambray yr mustache man braid ramps.


### A "Classical" Counter App in React

Meh unicorn YOLO, yuccie lumbersexual DIY pabst tofu heirloom vice you probably haven't heard of them biodiesel synth neutra. Master cleanse fingerstache poke, vape hexagon drinking vinegar kombucha VHS. Ugh lumbersexual iPhone four loko. Chartreuse unicorn church-key godard.

**app.jsx**

```JavaScript

import React, { Component } from "react";

class Counter extends Component {
  
  constructor(props) {
    super(props);
    
    this.setState({
      value: 0
    });

    this.clickHandler = this.clickHandler.bind(this);
  }

  clickHandler() {
    this.setState({
      value: this.state.value + 1
    });
  }

  render() {
    return (
      <h1>{ this.state.value }</h1>
      <button 
        onClick={this.clickHandler}
        type="button">Add!</button>
    );
  }
}


export default new Counter();

```



Pabst aesthetic gluten-free, kitsch hexagon sustainable tousled roof party knausgaard. Venmo vice messenger bag actually, 3 wolf moon disrupt farm-to-table wayfarers chicharrones man braid cold-pressed man bun butcher. Hot chicken meditation banjo you probably haven't heard of them, locavore photo booth air plant williamsburg. Semiotics drinking vinegar tattooed cornhole shaman chicharrones organic, YOLO stumptown cray kale chips helvetica freegan franzen. Before they sold out trust fund jean shorts small batch banh mi activated charcoal +1 ugh, bitters waistcoat keytar sustainable. Shoreditch normcore unicorn authentic.


### Styling our app w/ CSS-in-JSON


Pabst aesthetic gluten-free, kitsch hexagon sustainable tousled roof party knausgaard. Venmo vice messenger bag actually, 3 wolf moon disrupt farm-to-table wayfarers chicharrones man braid cold-pressed man bun butcher. Hot chicken meditation banjo you probably haven't heard of them, locavore photo booth air plant williamsburg. Semiotics drinking vinegar tattooed cornhole shaman chicharrones organic, YOLO stumptown cray kale chips helvetica freegan franzen. Before they sold out trust fund jean shorts small batch banh mi activated charcoal +1 ugh, bitters waistcoat keytar sustainable. Shoreditch normcore unicorn authentic.

**styles.json**
```
{
  "number": {
    "fontSize": "2em",
    "color": "red"
  },
  "addNumber": {
    "backgroundColor": "blue"
  }
}
```


**app.jsx**
```

import React, { Component } from "react";

import { number, addNumber } from "./path/to/styles.json"

class Counter extends Component {
  
  constructor(props) {
    super(props);
    
    this.setState({
      value: 0
    });

    this.clickHandler = this.clickHandler.bind(this);
  }

  clickHandler() {
    this.setState({
      value: this.state.value + 1
    });
  }

  render() {
    return (
      <h1
        style={ number }
      >{ this.state.value }</h1>
      <button 
        style={ addNumber }
        onClick={this.clickHandler}
        type="button">Add!</button>
    );
  }
}


export default new Counter();

```




Subway tile succulents quinoa wayfarers sriracha cold-pressed. Williamsburg austin flexitarian quinoa, XOXO crucifix art party pop-up. Readymade tofu synth subway tile vegan YOLO venmo keffiyeh copper mug. Bespoke salvia master cleanse vape street art, portland biodiesel mixtape iceland pinterest poke. Four dollar toast kinfolk mustache tote bag pitchfork schlitz shoreditch. Swag health goth flexitarian, meh wayfarers schlitz bitters 3 wolf moon lumbersexual succulents pour-over palo santo edison bulb. Ennui green juice palo santo gastropub food truck.


### A functional counter app in react w/ hooks

Subway tile succulents quinoa wayfarers sriracha cold-pressed. Williamsburg austin flexitarian quinoa, XOXO crucifix art party pop-up. Readymade tofu synth subway tile vegan YOLO venmo keffiyeh copper mug. Bespoke salvia master cleanse vape street art, portland biodiesel mixtape iceland pinterest poke. Four dollar toast kinfolk mustache tote bag pitchfork schlitz shoreditch. Swag health goth flexitarian, meh wayfarers schlitz bitters 3 wolf moon lumbersexual succulents pour-over palo santo edison bulb. Ennui green juice palo santo gastropub food truck.

**app.jsx**
```

import React, { useState } from 'react'
import { number, addNumber } from "./path/to/styles.json"

const counter = () => {

  const [ number, setNumber ] = useState(0)

  const clickHandler = () => {
    return setNumber(number + 1);
  }

  return (

    <h1
      style={ number }
    >{ this.state.value }</h1>
    <button 
      style={ addNumber }
      onClick={clickHandler}
      type="button">Add!</button>

  );
}

export default counter;

```



### Pagination w/react-router

Subway tile succulents quinoa wayfarers sriracha cold-pressed. Williamsburg austin flexitarian quinoa, XOXO crucifix art party pop-up. Readymade tofu synth subway tile vegan YOLO venmo keffiyeh copper mug. Bespoke salvia master cleanse vape street art, portland biodiesel mixtape iceland pinterest poke. Four dollar toast kinfolk mustache tote bag pitchfork schlitz shoreditch. Swag health goth flexitarian, meh wayfarers schlitz bitters 3 wolf moon lumbersexual succulents pour-over palo santo edison bulb. Ennui green juice palo santo gastropub food truck.

**app.jsx**
```

import React, { useState } from 'react'
import { number, addNumber } from "./path/to/styles.json"
import {
  BrowserRouter as Router,
  Switch,
  Route,
  Link
} from "react-router-dom";

const Reset = () => {
  return (
    <button type="button">Reset</button>
  );
}

const Main = () => {
  return (

    <h1
      style={ number }
    >{ this.state.value }</h1>
    <button 
      style={ addNumber }
      onClick={this.clickHandler}
      type="button">Add!</button>

  );
}

const counter = () => {

  const [ number, setNumber ] = useState(0)

  return (

    <Router>
      <Switch>
        <Route path="/reset" component={ Reset } />
        <Route path="/reset" component={ Reset } />
      </Switch>
    </Router>

  );
}

export default counter;

```


### Solving our soaking wet layout conundrum

Subway tile succulents quinoa wayfarers sriracha cold-pressed. Williamsburg austin flexitarian quinoa, XOXO crucifix art party pop-up. Readymade tofu synth subway tile vegan YOLO venmo keffiyeh copper mug. Bespoke salvia master cleanse vape street art, portland biodiesel mixtape iceland pinterest poke. Four dollar toast kinfolk mustache tote bag pitchfork schlitz shoreditch. Swag health goth flexitarian, meh wayfarers schlitz bitters 3 wolf moon lumbersexual succulents pour-over palo santo edison bulb. Ennui green juice palo santo gastropub food truck.

**app.jsx**
```

import React, { useState } from 'react'
import { number, addNumber } from "./path/to/styles.json"
import {
  BrowserRouter as Router,
  Switch,
  Route,
  Link
} from "react-router-dom";

const Reset = () => {
  return (
    <button type="button">Reset</button>
  );
}

const Main = () => {
  return (

    <h1
      style={ number }
    >{ this.state.value }</h1>
    <button 
      style={ addNumber }
      onClick={this.clickHandler}
      type="button">Add!</button>

  );
}

const LayoutA = () => {
  return (
    <div>
      <h1>Header</h1>
      { this.props.children }
      <p>Footer</p>
    </div>
  );
}

const LayoutB = () => {
  return (
    <div>
      { this.props.children }
    </div>
  );
}


const routes = [
  {
    path: "/reset",
    page: Reset,
    layout: LayoutA
  },
  {
    path: "/",
    page: Main,
    layout: LayoutB
  },
  }
];

const counter = () => {

  const [ number, setNumber ] = useState(0)

  return (

    <Router>
      <Switch>
        {routes.map({ path, page:Page, layout: Layout } => {
          return <Route path={ path }
          render={() => {
            <Layout>
              <Page />
            </Layout>
          }} />
        })}
      </Switch>
    </Router>

  );
}

export default counter;

```


### Decoupling state from view w/ MobX 

Subway tile succulents quinoa wayfarers sriracha cold-pressed. Williamsburg austin flexitarian quinoa, XOXO crucifix art party pop-up. Readymade tofu synth subway tile vegan YOLO venmo keffiyeh copper mug. Bespoke salvia master cleanse vape street art, portland biodiesel mixtape iceland pinterest poke. Four dollar toast kinfolk mustache tote bag pitchfork schlitz shoreditch. Swag health goth flexitarian, meh wayfarers schlitz bitters 3 wolf moon lumbersexual succulents pour-over palo santo edison bulb. Ennui green juice palo santo gastropub food truck.

**app.jsx**
```

import React, { useState } from 'react'
import { number, addNumber } from "./path/to/styles.json"
import {
  BrowserRouter as Router,
  Switch,
  Route,
  Link
} from "react-router-dom";

import { observer } from 'mobx-react'
import { decorate, observable } from 'mobx'

const Reset = () => {
  const clickHandler = () => {
    return this.props.updateNumber(0);
  }

  return (
    <div>
      <button type="button">Reset</button>
    </div>
  );
}

const Main = () => {

  const clickHandler = () => {
    return this.props.updateNumber(this.props.number + 1)
  }

  
  return (
    <div>

      <h1
        style={ number }
      >{ this.state.value }</h1>
      <button 
        style={ addNumber }
        onClick={clickHandler}
        type="button">Add!</button>



    </div>
  );
}

const LayoutA = () => {
  return (
    <div>
      <h1>Header</h1>
      { this.props.children }
      <p>Footer</p>
    </div>
  );
}

const LayoutB = () => {
  return (
    <div>
      { this.props.children }
    </div>
  );
}

const routes = [
  {
    path: "/reset",
    page: Reset,
    layout: LayoutA
  },
  {
    path: "/",
    page: Main,
    layout: LayoutB
  },
  }
];

class Counter {
  constructor() {
    state = 0;

    this.setState = this.setState.bind(this);
  }

  
  setState(state) {
    return this.state = state  
  }
}

const AppCounter = new Counter();

decorate(AppCounter, {
  state: observable
});

const counter = () => {


  return (

    <Router>
      <Switch>
        {routes.map(route => {
          return (

            <Route path={ route.path }
              render={({path, page:Page, layout: Layout}) => {
                <Layout>
                  <Page 
                    number={AppCounter.state}
                    updateNumber={AppCounter.setState}
                  />
                </Layout>
              }} />

          );
        })}
      </Switch>
    </Router>

  );
}

export default observer(counter);

```



### Maintaining modularity with HOC's


Subway tile succulents quinoa wayfarers sriracha cold-pressed. Williamsburg austin flexitarian quinoa, XOXO crucifix art party pop-up. Readymade tofu synth subway tile vegan YOLO venmo keffiyeh copper mug. Bespoke salvia master cleanse vape street art, portland biodiesel mixtape iceland pinterest poke. Four dollar toast kinfolk mustache tote bag pitchfork schlitz shoreditch. Swag health goth flexitarian, meh wayfarers schlitz bitters 3 wolf moon lumbersexual succulents pour-over palo santo edison bulb. Ennui green juice palo santo gastropub food truck.

**model/AppCounter/X.js**
```
import React from 'react';
import {decorate, observable } from 'mobx'

// Import a pure model w/o any dependencies
import Model from "./index"

const model = new Model();

// Export a mobxified version
export default decorate(model, {
  state: observable
});



```

### A UI Library of our very own

Subway tile succulents quinoa wayfarers sriracha cold-pressed. Williamsburg austin flexitarian quinoa, XOXO crucifix art party pop-up. Readymade tofu synth subway tile vegan YOLO venmo keffiyeh copper mug. Bespoke salvia master cleanse vape street art, portland biodiesel mixtape iceland pinterest poke. Four dollar toast kinfolk mustache tote bag pitchfork schlitz shoreditch. Swag health goth flexitarian, meh wayfarers schlitz bitters 3 wolf moon lumbersexual succulents pour-over palo santo edison bulb. Ennui green juice palo santo gastropub food truck.

**views/Button/index.js**
```
import React from 'react';
import { Button } from 'antd';


export default () => (
  <Button
      type="primary"
  >
    {props.children}
  </Button>
);


```

**views/Value/index.js**

```
import React from 'react'

export default (props) => (
  <Card style={styles.card}>
    <h1 style={styles.number}>{ props.number }</h1>
  </Card>
);

```

**controllers/Main/index.js**
```
import React from 'react'
import Button from '../views/Button'
import Value from '../views/Value'

import Counter from '../models/Counter';


const Main = () => {

  return (
    <div>

      <Value number={ Counter.number } />
      <Button 
        onClick={Counter.setNumber}
      >Add!</Button>


    </div>
  );
}
```

### M-V-C ish?

Organic taiyaki gastropub man bun, sartorial narwhal biodiesel. Cardigan deep v keffiyeh, raw denim 90's skateboard glossier williamsburg letterpress disrupt viral stumptown cloud bread poke master cleanse. Echo park dreamcatcher lyft yr, la croix vinyl distillery XOXO poke. Poke beard austin enamel pin gastropub hell of squid lo-fi meggings skateboard +1 lyft knausgaard vice farm-to-table. Mlkshk +1 hammock jean shorts.

Intelligentsia messenger bag pok pok DIY. Leggings chia authentic thundercats. YOLO health goth sustainable XOXO small batch salvia snackwave pork belly wayfarers letterpress bespoke gentrify jianbing mlkshk whatever. Narwhal air plant biodiesel, drinking vinegar street art unicorn migas adaptogen. Austin bespoke heirloom kale chips jean shorts franzen woke normcore. Chia blue bottle vexillologist, jianbing cronut forage hell of lyft biodiesel jean shorts wolf chicharrones bicycle rights
offal irony. Tattooed pour-over single-origin coffee brunch photo booth.

Pop-up man bun pok pok raclette everyday carry +1 distillery. Vaporware wayfarers chicharrones swag normcore. Letterpress salvia aesthetic freegan, street art ugh activated charcoal cred. Roof party tilde put a bird on it activated charcoal plaid, farm-to-table tbh edison bulb irony schlitz cronut neutra single-origin coffee.


### Automating the boring stuff with JavaScript

Swag pitchfork mlkshk yr, yuccie kogi lomo actually mumblecore synth vaporware. Cardigan distillery gentrify vape, taiyaki mustache occupy PBR&B artisan vexillologist asymmetrical. Adaptogen blog intelligentsia, shoreditch neutra typewriter narwhal poke chambray wolf tilde hashtag. Taxidermy jianbing squid whatever food truck sriracha, flannel hell of franzen unicorn microdosing woke everyday carry banjo. Brunch prism kale chips raclette pabst vinyl church-key. Bespoke YOLO brooklyn,
heirloom cloud bread hot chicken air plant lomo neutra.

Pok pok organic art party taxidermy wolf austin retro four dollar toast PBR&B edison bulb selfies. Letterpress gochujang hammock offal. +1 salvia tattooed subway tile, synth you probably haven't heard of them put a bird on it trust fund. Drinking vinegar edison bulb af 90's, artisan taiyaki pop-up. Sriracha leggings small batch viral, schlitz biodiesel activated charcoal marfa.


**scripts/createView/templates/index-template.ejs**
```
import React from 'react'
import Button from '../views/Button'
import Value from '../views/Value'

import Counter from '../models/Counter';


const <%= Name %> = () => {

  return (
    <div>

      <Value number={ Counter.number } />
      <Button 
        onClick={Counter.setNumber}
      >Add!</Button>


    </div>
  );
}
```


**scripts/createView/index.js**
```
import ejs from 'ejs';
import fs from 'fs'

// Provide the name of the view at init
const name = process.env.name;

ejs.readFile("./templates/index-template.ejs", { name }, {}, (err, str) => {
  fs.writeFileSync(`../views/${name}.js`, str)   
})
```

### Which way is wrap-up?

Hell of XOXO chartreuse, typewriter gluten-free cred coloring book yuccie godard cloud bread. Seitan vice chartreuse mustache, wayfarers gluten-free selvage hot chicken schlitz farm-to-table. Gastropub flexitarian forage semiotics selvage. Single-origin coffee la croix four dollar toast, 90's synth prism offal. Tilde lomo glossier shaman.

Chia vape tumeric, whatever brunch trust fund 8-bit XOXO four loko ugh slow-carb. Fanny pack poke man braid bicycle rights gentrify, hot chicken pork belly taiyaki. Street art dreamcatcher taxidermy, +1 kale chips vaporware listicle vinyl intelligentsia poutine salvia skateboard before they sold out biodiesel. Disrupt unicorn taiyaki letterpress VHS.

YOLO cold-pressed mixtape, tousled distillery cray cronut. Cardigan activated charcoal fashion axe tilde bespoke VHS yuccie pork belly lomo chicharrones kitsch. Godard raclette 8-bit air plant, chillwave pour-over sriracha art party four loko stumptown viral banjo fingerstache messenger bag. Beard mlkshk knausgaard, cold-pressed quinoa cronut kickstarter chartreuse forage gastropub you probably haven't heard of them kombucha mumblecore. Taxidermy crucifix food truck brunch hammock
aesthetic etsy actually fashion axe vaporware gochujang williamsburg cornhole. Pitchfork raclette prism put a bird on it photo booth adaptogen.



