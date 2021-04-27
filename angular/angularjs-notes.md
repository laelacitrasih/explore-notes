# AngularJS notes
## started
- docs: https://angular.io/guide/setup-local
- install: npm install -g @angular/cli
	
	
## create workspace / project
```
ng new <name app>

```
- add angular routing? yes
- stylesheet format? SCSS


## run the application
```
cd <name app>
ng serve --open 
```
or
```
cd <name app>
ng s --o 
```

- angular app will running in port 4200 or localhost:4200


## create new component
```
ng generate component <name component>
```
or/ example:
```
ng g c login
```
or/ example with folder:
```
ng g c auth/login
```

- the new component will upated in the app.module, there will a new import component and declaration


## navigation
- all routing set up in app-routing.module.ts 

- declare paths and components in Routes
example:
```
{
	path: 'login',
	component: LoginComponent //the class of the login page
}
```
- write router-outlet in app.component
```
<router-outlet></router-outlet>
```
the function is to inject the page declared before  
- run the app
- to try the path, use the / and path declared before. 
example:
```
localhost:4200/login
```
will output "login works!" if success
- to move page, href in angular use "routerLink"
example: 
```
<button routerLink='/login'>LOGIN</button>
```
- to declare default page or blank path navigation
example:
```
{
	path: '',
	pathMatch: full,
	redirectTo: '/login'
}
```
- to declare page from other module
example:
```
{
	path: <path name>
	loadChildren: () => import (`<path module>`).then(mod=>mod.<module class name>)
}
```

## module / add new module
```
ng g module <module name>
```
- to add new component in new module, use query create new component
- in the new module, it can added Routes in <modulename>.module.ts, required to import {Routes} from '@angular/router';
example:
```
import {Routes} from '@angular/router';

const routes: Routes = [
	{
		path: '',
		component: <component name>,
		children: [
			{
				path: '<path name>',
				component: '<component class name >'
			}
		]
	}
]
```
then, add variable in @NgModule in imports
```
imports:[
	RouterModule.forChild(routes)
]
```


## server-angular comunication
- import HttpClientModule pada app.module.ts
```
import { HttpClientModule } from '@angular/common/http';
```
- create service
```
ng g service services/api
```
- write code in api.service.ts
```
```
