---
title: Getting Started for Angular FileExplorer
description: Getting Started for Angular FileExplorer
platform: Angular
control: FileExplorer
documentation: Ug
keywords: ejfileexplorer, js fileexplorer, fileexplorer
---

# Getting Started

This section explains briefly about how to create a **FileExplorer** control in your application with **Angular**.

## Create FileExplorer in Angular Application using Web pack

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [Web pack starter](https://github.com/syncfusion/angular2-seeds) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/angular2-seeds

 > cd angular2-seeds

 > npm install
{% endhighlight %}

The below steps describes to add fileexplorer component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular source component(s) from the below build location and add it in `src/app/ej` folder.

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\angular2\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `fileexplorer` folder inside `src/app` folder.

* Create `fileexplorer.component.html` view file inside `src/app/fileexplorer` folder and render ejFileExplorer Angular component using the below code example. 

{% highlight html %}
    <ej-fileexplorer id="fileExplorer" 
       path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
       ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
       width="100%" minWidth="150px" fileTypes="*.png, *.gif, *.jpg, *.jpeg, *.docx"
       layout= "tile" style="display:block">
    </ej-fileexplorer>
{% endhighlight %}

* Create `fileexplorer.component.ts` model file inside the folder `src/app/fileexplorer` and create fileexplorer sample component using the below code example.

{% highlight javascript %}
import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './fileexplorer.component.html'
})
export class FileExplorerComponent { }
{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejFileExplorer component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing. 

* Now, we are going to configure the route navigation link for created FileExplorer sample in `src/app/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
	<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#fileexplorer" 
    [routerLink]="['/fileexplorer']">FileExplorer </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejFileExplorer sample component and define the route in `src/app/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { FileExplorerComponent } from './fileexplorer/fileexplorer.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'fileexplorer', component: FileExplorerComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejFileExplorer sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngular2Module } from 'ej-angular2';
import { AppComponent } from './app.component';
import { FileExplorerComponent } from './fileexplorer/fileexplorer.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngular2Module.forRoot(),
  RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , FileExplorerComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to FileExplorer tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

N> if you want to use other port, open `package.json` file, then change port in `--port 3000` script and also change the port in `config/webpack.dev.js`.

![](Getting-Started_images/Getting-Started_img1.jpeg)

## Create FileExplorer in Angular Application using SystemJS  

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [SystemJS starter](https://github.com/syncfusion/angular2-seeds/tree/systemjs) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/angular2-seeds/ -b systemjs

 > cd angular2-seeds

 > npm install
{% endhighlight %}

The below steps describes to add fileexplorer component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular source component(s) from the below build location and add it in `src/ej` folder.

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\angular2\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `fileexplorer` folder inside `src` folder.

* Create `fileexplorer.component.html` view file inside `src/fileexplorer` folder and render ejFileExplorer Angular component using the below code example. 

{% highlight html %}
    <ej-fileexplorer id="fileExplorer" 
        path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
	ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
	width="100%" minWidth="150px" fileTypes="*.png, *.gif, *.jpg, *.jpeg, *.docx" 
	layout= "tile" style="display:block">
    </ej-fileexplorer>
{% endhighlight %}

* Create `fileexplorer.component.ts` model file inside the folder `src/fileexplorer` and create fileexplorer sample component using the below code example.

{% highlight javascript %}
import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/fileexplorer/fileexplorer.component.html'
})
export class FileExplorerComponent { }
{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejFileExplorer component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing. 

* Now, we are going to configure the route navigation link for created FileExplorer sample in `src/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
	<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in"
    href="#fileexplorer" [routerLink]="['/fileexplorer']">FileExplorer </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejFileExplorer sample component and define the route in `src/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { FileExplorerComponent } from './fileexplorer/fileexplorer.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'fileexplorer', component: FileExplorerComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejFileExplorer sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngular2Module } from 'ej-angular2';
import { AppComponent } from './app.component';
import { FileExplorerComponent } from './fileexplorer/fileexplorer.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
   imports: [BrowserModule, FormsModule, HttpModule, EJAngular2Module.forRoot(), 
   RouterModule.forRoot(rootRouterConfig, { useHash: true })],
   declarations: [. . . . , FileExplorerComponent],
   bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to FileExplorer tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

![](Getting-Started_images/Getting-Started_img1.jpeg)

