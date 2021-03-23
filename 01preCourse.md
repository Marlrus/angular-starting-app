# Angular course 2021

> Course by Maximilian Schwarzmuller

Angular is a framework for SPAs. Angular has a lot of versions. The first one was AngularJS (Angular1) which had a lot of issues and was re written in Angular 2. There are 9-10 angular versions. Since Angular 2 every 6 months a new version is realeased, and the differences are minimal and contain non-breaking synax changes. Angular refers to any version of Angular after Angular 2.

## Angular CLI

Angular is elaborate in the build flow, the CLI helps us do this. The CLI uses Node and NPM to manage the building and creation. We create a new app with **ng new** and just browse the files.

## Live update using ngModel

We erase the app html and create an input and a p tag. On the input we place **ngModel** but it won't work becuase to use this feature we need to import the module.

Angular works using different modules depending on the features that we want to add to our application. These are done in the **app.module.ts** file. We need the **FormsModule** to use this directive:

```typescript
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";
import { FormsModule } from "@angular/forms";

import { AppComponent } from "./app.component";

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, FormsModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

This gives us access to the directive through the **form module**. Once we do this, we can see our form change in real time.

## Course Structure

- Basics: How files are related in an Angular project
- Components and databinding: How you display items in the DOM and how to use data in them.
- Directives: Learning and creating custom directives.
- Services & Dependency Injection: How to communicate parts of the apps with each others.
- Routing: How to manange URLs although we are in an SPA.
- Observables: Working with async code.
- Forms: How to handle forms in any application.
- Pipes: Transforming the output to display at runtime.
- HTTP: Connecting to servers.
- Authentication: What and how to add to an app.
- Optimizations and NgModules: Splitting files in an app
- Deployment: Moving our app out of local.
- Animations and testing

These things will be done in our application.

## TS and Angular

A superset to JS that has static typing. This allows us to check code as we run. It is compiled in the end to JS, this is done by the CLI.

## Bootstrap

For styling this project, we will use bootstrap. We run `npm i bootstrap@4`. Once we do this, we need to import the css into the projct. We do this in the **angular.json** file:

```json
"styles": [
  "node_modules/bootstrap/dist/css/bootstrap.min.css",
  "src/styles.css"
],
```

We need to specify the path to the styles file in order to have access to bootstrap. We need to restart our server to see these changes. To verify we did the import correctly we can go to the dev tools Sources tab and look at the **styles.css** file and we should see bootstrap mentioned:

```css
/*!
 * Bootstrap v4.6.0 (https://getbootstrap.com/)
 * Copyright 2011-2021 The Bootstrap Authors
 * Copyright 2011-2021 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/main/LICENSE)
/* You can add global styles to this file, and also import other style files */
```

This file will contain the minified version of Bootstrap which is massive.
