# Nexter Project - Front End
`Live:` https://insertmike.github.io/nexter-project/   

A CSS Grid based design for a real estate website.
## Features
- Fully responsive [ *Desktop First Approach* ]
- Written completely in *HTML & CSS*    
- Used the <a href="https://sass-guidelin.es/#the-7-1-pattern" target="_blank">*7-1 SASS pattern*</a>  &  <a href="https://en.bem.info/methodology/" target="_blank">*BEM*</a>   to create scalable and maintainable code.    
 
 Designed by Jonas Schmedtmann, implemented by me.
 ## Project Overview
- ### Overall Approach
   The overall layout is a `CSS Grid` :
    
   ![grid](https://user-images.githubusercontent.com/45242072/57200360-ef232400-6f82-11e9-94c5-ec9fe1a409c2.jpg)

  - Naming the columns made the positioning of the components very easy.  
  
  - Using the Grid system gave me the opportunity to make the overall layout responsive with very
little media queries.
  
  Code behind the layout:
  
  ```scss
  .container{
      display: grid;

      grid-template-rows: 80vh min-content 40vw repeat(3, min-content); 

      grid-template-columns: [sidebar-start] 8rem [sidebar-end full-start] minmax(6rem, 1fr) 
      [center-start] repeat(8, [col-start] minmax((min-content), 14rem) [col-end]) [center-end]
      minmax(6rem, 1fr) [full-end];

  }
  ```

 ## Responsivness
 
   <div align="center">
   
   #### Using Grid for Overall Layout:
   
   ![responsive](https://user-images.githubusercontent.com/45242072/57200796-fbf64680-6f87-11e9-8c8d-5649af32ed72.gif)
        
   </div>
 
   <div align="center">
   
   #### Using Grid for Homes Section:
   
   ![homes](https://user-images.githubusercontent.com/45242072/57200951-cfdbc500-6f89-11e9-8238-3c9d6c1e8574.gif)
    
    
   #### Using Grid for a Gallery:
   
   ![gallery](https://user-images.githubusercontent.com/45242072/57200853-b8e8a300-6f88-11e9-802d-ceb64fb2db3e.jpg)
        
   </div>



## NPM Dev Packages:
```json
 "devDependencies": {
    "autoprefixer": "^7.1.4",
    "concat": "^1.0.3",
    "node-sass": "^4.5.3",
    "npm-run-all": "^4.1.1",
    "postcss-cli": "^4.1.1"
  }
```
## NPM Scripts:
```json
  "scripts": {
    "watch:sass": "node-sass sass/main.scss css/style.css -w",
    "devserver": "live-server --browser=firefox",
    "start": "npm-run-all --parallel devserver watch:sass",
    "compile:sass": "node-sass sass/main.scss css/style.comp.css",
    "prefix:css": "postcss --use autoprefixer -b \"last 10 versions\" css/style.comp.css -o css/style.prefix.css",
    "compress:css": "node-sass css/style.prefix.css css/style.css --output-style compressed",
    "build:css": "npm-run-all compile:sass prefix:css compress:css"
   }
```      
