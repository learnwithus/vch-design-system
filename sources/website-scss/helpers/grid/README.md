# Cossette RAD — RAD GRID CSS


## What does it do?

allow you to integrate DOM element based on a designed grid


## What does it include ?

### _rad-grid.scss

the main grid file where you can setup the margins, width , gutters of the grid 

### _rad-grid.classes.scss

the grid file where css classes are defined by breakpoints

### _rad-grid.helpers.scss

A grid overlay that is displayed over the html body and works with the rad-grid setup



 #### Basic exemple 

 wrap DOM Element onto a div.container 

```
<div class="container">
  <div class="my-first-element col-12 col-md-8 col-md-offset-2"></div>
</div>
```