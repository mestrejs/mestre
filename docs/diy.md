Last login: Sun Mar 29 23:39:33 on ttys010
Victors-MacBook-Pro:client hugesuccess$ sudo vim
Password:
Victors-MacBook-Pro:client hugesuccess$ ls
README.md node_modules  package.json  public    src   tsconfig.json yarn-error.log  yarn.lock
Victors-MacBook-Pro:client hugesuccess$ ;s
-bash: syntax error near unexpected token `;'
Victors-MacBook-Pro:client hugesuccess$ ls
README.md node_modules  package.json  public    src   tsconfig.json yarn-error.log  yarn.lock
Victors-MacBook-Pro:client hugesuccess$ vim













































 1 DIY.md                                                                                                                                       X 
 
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
 
 Hell of XOXO chartreuse, typewriter gluten-free cred coloring book yuccie godard cloud bread. Seitan vice chartreuse mustache, wayfarers gluten-  free selvage hot chicken schlitz farm-to-table. Gastropub flexitarian forage semiotics selvage. Single-origin coffee la croix four dollar toast,  90's synth prism offal. Tilde lomo glossier shaman.
 
 Chia vape tumeric, whatever brunch trust fund 8-bit XOXO four loko ugh slow-carb. Fanny pack poke man braid bicycle rights gentrify, hot chicken  pork belly taiyaki. Street art dreamcatcher taxidermy, +1 kale chips vaporware listicle vinyl intelligentsia poutine salvia skateboard before     they sold out biodiesel. Disrupt unicorn taiyaki letterpress VHS.
 
 YOLO cold-pressed mixtape, tousled distillery cray cronut. Cardigan activated charcoal fashion axe tilde bespoke VHS yuccie pork belly lomo       chicharrones kitsch. Godard raclette 8-bit air plant, chillwave pour-over sriracha art party four loko stumptown viral banjo fingerstache         messenger bag. Beard mlkshk knausgaard, cold-pressed quinoa cronut kickstarter chartreuse forage gastropub you probably haven't heard of them     kombucha mumblecore. Taxidermy crucifix food truck brunch hammock
 aesthetic etsy actually fashion axe vaporware gochujang williamsburg cornhole. Pitchfork raclette prism put a bird on it photo booth adaptogen.
 

