---
layout: post
title: Getting started with Essential JS 1 for Angular with SystemJS
description: Learn how to integrate Essential JS 1 Angular component into SystemJS loader Angular application environment..
platform: Angular
control: Introduction
documentation: ug
---


# Getting started with SystemJS

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [SystemJS starter](https://github.com/syncfusion/angular2-seeds/tree/systemjs) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/angular2-seeds/ -b systemjs 

 > cd angular2-seeds 

 > npm install 
{% endhighlight %}

N> The cloned application is fully configured to work with Essential Studio for JavaScript Angular components, in which we configured our [ej-angular2](https://github.com/syncfusion/ej-angular2) library and necessary changes to consume our Angular components.

## What is in Syncfusion cloned Angular seed.?
The cloned Angular seed consists of files in the following structure. The files in the `src` folder is used for logical functionalities in our application. The other files available outside the src folder is used to build, bundle and deploy the application. 

* src
        * app.component.ts
        * app.module.ts
        * main.ts
* index.html
* package.json
* systemjs.config.js
* tsconfig.json

The below table depicts the purpose of files in the above structure.

<table>
<tr>
<th>Files  </th>
<th>Purpose </th>
</tr>
<tr>
<td>src/app.component.ts </td>
<td>It is a top-level component where all the functionalities are lies in this component</td>
</tr>
<tr>
<td>src/app.module.ts </td>
<td>It tells the angular how to construct and bootstrap the app in the root module. In our application, it bootstraps the `AppComponent` to launch the application.    </td>
</tr>
<tr>
<td>src/main.ts</td>
<td>The main entry point of the application, in which we kick-off our application by importing the `AppComponent` and bootstrapping it. </td>
</tr>
<tr>
<td>package.json </td>
<td>It serves as documentation for what packages our project depends on. It allows you to specify the name, version, scripts, dependencies of a package. <ul> <li> Name- Name of our package </li> <li> Version- Current version of package </li> <li> Scripts- It runs at various time of life cycle of package </li> <li> Dependencies- It is used for production in our application </li> </ul> In our application, we used name, version, scripts and dependencies in package.json file
</td>
</tr>
<tr>
<td> index.html  </td>
<td> It is the host page of application. It loads all needed libraries and essential scripts in a prescribed order. It holds a custom tag which is used to load the meta data of `AppComponent`. <br> E.g.: `ej-app` is the custom tag in our cloned seed application. </td>
</tr>
<tr>
<td>systemjs.config.js </td>
<td>It contains the mapping information of files, which are used for developing Angular application. It tells the SystemJS module loader where to find modules referenced in Angular component imports statements.</td>
</tr>
<tr>
<td>tsconfig.json</td>
<td>All typescript files need to be transpiled/compiled to native JavaScript files so that we can run them on browser. To accomplish this, we need to add `Typescript Configuration file` called as tsconfig.json, which is used as input of typescript compiler(tsc) to transpile the typescript files.</td>
</tr>
</table>

## Syntax of Angular component

{% highlight ts %}

//import statements
import {Component} from '@angular/core';

@Component ({
         . . . .
         . . . .
         // Takes metadata object from exported class
         // It describes how the HTML template and component class work together 
})

export class ComponentName { 
         . . . .
         // Exports the metadata object to component 
}

{% endhighlight %}

N> We recommend you to go through the [quick start](https://angular.io/guide/quickstart) of Angular application to get deeper knowledge of setup and structure of the application.

## Consuming ej-angular2 library

The cloned application already configured with `ej-angular2` library to seamlessly work with Angular and Essential JavaScript components. The below steps describe, how the library consumed in the Angular seed application.

* To install this library, run the below command in the root of Angular application.

{% highlight javascript %}

npm install ej-angular2 --save

{% endhighlight %}

*	We can import this library in any Angular application's AppModule. Here we imported the `ej-angular2` library in our cloned application.

{% highlight ts %}

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';
// Import the library module
import { EJAngular2Module } from 'ej-angular2';

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule,LibraryModule, EJAngular2Module.forRoot()],
  providers: [],
  bootstrap: [AppComponent]
})

export class AppModule { }

{% endhighlight %}

N> The Syncfusion JavaScript Component needs dependencies `jquery` and `jsrender` which need to loaded through systemjs loader in `systemjs.config.js` file. Refer the [link](https://github.com/syncfusion/angular2-seeds/blob/systemjs/systemjs.config.js/#L27-L28) for code snippet.

{% highlight javascript %}

'jquery': 'npm:jquery/dist/jquery.min.js',
'jsrender': 'npm:jsrender/jsrender.min.js',

{% endhighlight %}


Now we can render any Syncfusion JavaScript Angular components in Angular application which will be discuss in the next section.

##  Adding sample with seed application

* Create `dialog` folder inside `src` folder.

* Create `dialog.component.html` view file inside `src/dialog` folder and render ejDialog Angular component using the below code example.

{% highlight html %}

<div id="parent" >
	<input id="btnOpen" style="height: 30px" type="button" ej-button class="ejinputtext" value="Click to open Dialog" (click)="onClick($event)" *ngIf="button_display" />
	<ej-dialog id="basicDialog" #dialog title="Facebook" [(enableResize)]="resize" containment="#parent" (close)="onClose($event)">
		Facebook is an online social networking service headquartered in Menlo Park, California. Its website was launched on February
		4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo Saverin, Andrew McCollum, Dustin
		Moskovitz and Chris Hughes. The founders had initially limited the website's membership to Harvard students, but later
		expanded it to colleges in the Boston area, the Ivy League, and Stanford University. It gradually added support for students
		at various other universities and later to high-school students.
	</ej-dialog>
</div>


{% endhighlight %}

* Create `dialog.component.ts` model file inside the folder `src/dialog` and create sample component using the below code example.

{% highlight ts %}

import { Component, ViewEncapsulation, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/dialog/dialog.component.html'
})
export class DialogComponent {
  resize: boolean;
  button_display: boolean;
  @ViewChild('dialog') dialog: EJComponents <any,any>;
    constructor() {
    this.resize = false;
    this.button_display = false;
  }
  //Button click event handler to open the ejDialog
  onClick(event) {
   this.button_display = false;
   this.dialog.widget.element.ejDialog('open');
  }
  //Dialog close event handler
  onClose(event) {
    this.button_display = true;
  }
}

{% endhighlight %}

## Configure the routes for the Router

Before adding router configuration for above created ejDialog component, we recommend you to go through the [Angular Routing](https://angular.io/guide/router) configuration to get the deeper knowledge about Angular routing.

* Now, we are going to configure the route navigation link for created Dialog sample in `src/app.component.html` file.

{% highlight html %}

<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#dialog" [routerLink]="['/dialog']">Dialog </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>

{% endhighlight %}

* Import the ejDialog sample component and define the route in `src/app.routes.ts` file.

{% highlight ts %}

import { Routes } from '@angular/router';
. . . . 
import { DialogComponent } from './dialog/dialog.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'dialog', component: DialogComponent }
];

{% endhighlight %}

* Import and declare the ejDialog sample component into `app.module.ts` like the below code snippet.

{% highlight ts %}

import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngular2Module } from 'ej-angular2';
import { AppComponent } from './app.component';
. . . . .
import { DialogComponent } from './dialog/dialog.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngular2Module.forRoot(), RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , DialogComponent],
  bootstrap: [AppComponent]
})
export class AppModule { } }) 
export class AppModule { }

{% endhighlight %}

Refer the below codes to create the application.

{% tabs %}

{% highlight ts %}

// Refer the code for app.component.ts file (src/app.component.ts)

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: [./app.component.html]
})
export class AppComponent { }

{% endhighlight %}

{% highlight ts %}

// Refer the code for app.module.ts file (src/app.module.ts)

import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { RouterModule } from '@angular/router';
import { FormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';

import { EJAngular2Module } from 'ej-angular2';

import { AppComponent } from './app.component';
import { HomeComponent } from './home/home.component';
import { GridComponent } from './grid/grid.component';
import { DialogComponent } from './dialog/dialog.component';
import { rootRouterConfig } from './app.routes';

enableProdMode();

class CustomErrorHandler implements ErrorHandler {
  call(error, stackTrace = null, reason = null) {
    console.log(error + "\n" + stackTrace);
  }
  handleError(error: any): void {
    console.log(error);
  }
}

@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngular2Module.forRoot(), RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [AppComponent, HomeComponent, GridComponent, DialogComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }

{% endhighlight %}

{% highlight ts %}

// Refer the code for main.ts file (src/main.ts)

import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
import { AppModule } from './app.module';

platformBrowserDynamic().bootstrapModule(AppModule);

{% endhighlight %}

{% highlight html %}

<!-- Refer the code for app.component.html file (src/app.component.html)-->

<nav class="navbar navbar-default navbar-fixed-top" role="navigation">
	<div style="padding-left:0px;" class="collapse navbar-collapse" id="skeleton-navigation-navbar-collapse">
		<ul class="nav navbar-nav">
			<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#">Syncfusion Angular Seed</a></li>
			<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#home">Home</a></li>
			<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#grid">Grid</a></li>
			<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#dialog">Dialog</a></li>
		</ul>
	</div>
</nav>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

{% highlight ts %}

// Refer the code for app.routes.ts file(src/app.routes.ts)

import { Routes } from '@angular/router';
import { GridComponent } from './grid/grid.component';
import { HomeComponent } from './home/home.component';
import { DialogComponent } from './dialog/dialog.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    { path: 'home', component: HomeComponent },
    { path: 'grid', component: GridComponent },
    { path: 'dialog', component: DialogComponent }
];

{% endhighlight %}

{% highlight json %}

// Refer the code for package.json file 

{
  "name": "ejangular2-systemjs-starter",
  "version": "1.0.0",
  "repository": {
    "type": "git",
    "url": "git+https://github.com/syncfusion/angular2-seeds.git"
  },
  "description": "A systemjs starter for Angular",
  "scripts": {
    "start": "concurrently \"npm run tsc:w\" \"npm run lite\" ",
    "lite": "lite-server",
    "tsc": "tsc",
    "tsc:w": "tsc -w"
  },
  "keywords": [
    "syncfusion",
    "ej",
    "essential",
    "javascript",
    "Angular",
    "Angular 2",
    "angular2"
  ],
  "author": "Syncfusion Inc",
  "license": "SEE LICENSE IN README.md",
  "bugs": {
    "url": "https://github.com/syncfusion/angular2-seeds/issues"
  },
  "homepage": "https://github.com/syncfusion/angular2-seeds#readme",
  "dependencies": {
    "@angular/common": "~5.1.2",
    "@angular/compiler": "~5.1.2",
    "@angular/core": "~5.1.2",
    "@angular/forms": "~5.1.2",
    "@angular/http": "~5.1.2",
    "@angular/platform-browser": "~5.1.2",
    "@angular/platform-browser-dynamic": "~5.1.2",
    "@angular/router": "~5.1.2",
    "@angular/upgrade": "~5.1.2",
    "core-js": "^2.4.1",
    "reflect-metadata": "^0.1.3",
    "rxjs": "5.0.1",
    "systemjs": "0.19.40",
    "zone.js": "^0.7.4",
    "angular2-in-memory-web-api": "0.0.20",
    "bootstrap": "^3.3.6",
    "jquery": "^3.1.1",
    "jsrender": "^0.9.75",
    "syncfusion-javascript": "^15.3.29",
    "ej-angular2": "^15.3.29",
    "@types/ej.web.all": "^14.4.1",
    "@types/jquery": "2.0.34",
    "@types/es6-shim": "0.31.32",
    "@types/node": "6.0.52"
  },
  "devDependencies": {
    "concurrently": "^2.0.0",
    "lite-server": "^2.1.0",
    "typescript": "^2.1.4"
  }
}

{% endhighlight %}

{% highlight javascript %}

// Refer the code for systemjs.config.js file 

(function (global) {
  System.config({
    paths: {
      // paths serve as alias
      'npm:': 'node_modules/'
    },
    // map tells the System loader where to look for things
    map: {
      // our app is within the app folder
      app: 'src',
      // angular bundles
      '@angular/core': 'npm:@angular/core/bundles/core.umd.js',
      '@angular/common': 'npm:@angular/common/bundles/common.umd.js',
      '@angular/compiler': 'npm:@angular/compiler/bundles/compiler.umd.js',
      '@angular/platform-browser': 'npm:@angular/platform-browser/bundles/platform-browser.umd.js',
      '@angular/platform-browser-dynamic': 'npm:@angular/platform-browser-dynamic/bundles/platform-browser-dynamic.umd.js',
      '@angular/http': 'npm:@angular/http/bundles/http.umd.js',
      '@angular/router': 'npm:@angular/router/bundles/router.umd.js',
      '@angular/forms': 'npm:@angular/forms/bundles/forms.umd.js',
      // other libraries
      'rxjs': 'npm:rxjs',
      'angular2-in-memory-web-api': 'npm:angular2-in-memory-web-api',
      'jquery': 'npm:jquery/dist/jquery.min.js',
      'jsrender': 'npm:jsrender/jsrender.min.js',
      'jquery-validation': 'npm:jquery-validation/dist/jquery.validate.min.js',
      'syncfusion-javascript': 'npm:syncfusion-javascript',
      'ej-angular2': 'npm:ej-angular2'
    },
    // packages tells the System loader how to load when no filename and/or no extension
    packages: {
      app: {
        main: './main.js',
        defaultExtension: 'js'
      },
      rxjs: {
        defaultExtension: 'js'
      },
      'angular2-in-memory-web-api': {
        main: './index.js',
        defaultExtension: 'js'
      },
      'ej-angular2': {
        main: './src/index.js'
      },
      'syncfusion-javascript': {
        defaultExtension: 'js'
      }
    }
  });
})(this);

{% endhighlight %}

{% endtabs %}

## Running the application

* To run the application, execute below command.

{% highlight javascript %}

npm start

{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to Dialog tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files.

![Essential JS 1 for Angular with SystemJS](/angular/GettingStarted/Images/getting-started-output.png) 

## Demos

We have implemented our [Angular sample browser](http://ng2jq.syncfusion.com/) using Syncfusion Angular components.