# Basics

The file served by the server is actually the **index.html** file. If we see the file we don't have any scripts. However, if we inspect the page, we can see that at the bottom there are some script tags with a few files. These are managed by the CLI tool and hold the files required to render the components that we created inside our Angular application. The first code that gets executed in our app is what is inside the **main.ts** file. Here we can see that if the env is production, the enableProdmode() function is called. We also **bootstrap** a module called **AppModule**.

Inside the **app.module.ts** we have a section called **bootstrap** which is what tells Angular which components it should know at the point when our Index file is loaded. Components are a key feature in Angular. We have a root component, usually app, where we add other components to. Every component contains its style, template, and business logic.

## Manual component creation

We create a directory for our component **server** and inside we create the server.component.ts file. Components are just **classes**, however we need to tell Angular that this is not a regular TS class but a special class. We do this through the **@Component** decorator. This must be improted from angular core. When we do this we need to pass a configuration object to this decorator which gives Angular information about the component:

```typescript
import { Component } from "@angular/core";

@Component({
  selector: "app-server",
  templateUrl: "./server.component.html",
})
export class ServerComponent {}
```

Here we told angular that this class is for a component through the use of the decorator, we told it that it would be called **app-server** with the selector prop, and then we gave it a link to the template via the **templateUrl** prop. This template must be created by us because we are linking it as an external file. We create the basic template but we still cannot use the component.

## AppModule and component declaration

To use the component we need to add it to our module. Angular uses components to build web pages, and uses modules to bundle different pieces of the app into packages. For the majority of projects, the app.module.ts file will be enough. In this file we can see that this is also just a class, but we transform it through the use of the **NgModule** decorator, which also comes from angular core. The confifuration object has a few properties:

- **bootstrap** takes an array of Components and tells Angular which components it must be aware of when the application starts.
- **declarations** is where we register new component so that Angular knows which components are available for use.
- **imports** allows us to add new modules to extend the functionality and tools that Angular has.
- **providers** will be covered later.

Once we have our component registered we can use the component. We can use it in our app-component file.

## CLI Component creation

We can create CLI commands to create a component `ng g c servers`. This will do what we did manually, create the folder, files, and add the import to the module file. Inside of this file we create two instances of **app-server** and then add it to the app component. Here we see that we have two instances of app-server that are wrapped in our app-servers.
