# Angular Material Notes

## get started
- docs: https://material.angular.io/
- install (in the root angular app):
```
ng add @angular/material
```
- select starter theme
- set up typography styles? Yes

## add material component
- pick material need
- click API menu and copy the import component
- import the API component to the module that use the component
- write/add in the "imports:[]"
- write the mat (material) component where needed

### implement add material component in child module
- if the component are used in multiple module, so create new folder to store import the API components globaly
- create folder "material" in "app" folder
- create material.ts
- copy all module material design API module import
- export const material design that store all material design class
example: 
```
import {MatTableModule} from '@angular/material/table';
import {MatSortModule} from '@angular/material/sort';

export const MaterialDesign=[
    MatTableModule,
    MatSortModule
]
```
- import the class material design in module child / needed
example:
```
import {MaterialDesign} from '../material/material'
```
- if needed re-serve the app
