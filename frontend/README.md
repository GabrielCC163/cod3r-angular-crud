## Steps:

### Setup Angular and add Material package
```
$ sudo npm install -g @angular/cli

$ ng new frontend --minimal --inlineStyle=false --inlineTemplate=false --routing=true

$ cd frontend

$ ng add @angular/material (1º / y / y)
```

### Refactor app.component.ts and create src/app/app.component.html

```
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: 'app.component.html'
})
export class AppComponent {
  
}
```

### Import Material modules in app.module.ts

```
...
import { MatToolbarModule } from '@angular/material/toolbar';
import { MatSidenavModule } from '@angular/material/sidenav';
import { MatListModule } from '@angular/material/list';
...

...
imports: [
    ...
    MatToolbarModule,
    MatSidenavModule,
    MatListModule
    ...
  ],
...
```

## Utils:
### Create elements (g = generate)
* Component
```
  $ ng g c components/template/<component_name>
```
* Service
```
  $ ng g s services/product
```
* Directive
```
  $ ng g d directives/red
```

## Resume
```
* Modules (app.module.ts)

* Components (html, css, ts => app-home)

* Directives
  -> Attribute Directives => changes appearance and behavior of a component or another directive. (<i appRed>)
  
  -> Structural Directives => changes the layout adding or removing elements from DOM. (*ngIf, *ngFor, ...). 
  
* Bindings 
    -> Property Binding (dataSource) => attribute [id]
    -> Event Binding => event (click)
    -> One Way Data Binding (<input [value="nome"]>)
    -> Two Way Data Binding (<input [(ngModel)]="nome">)

* Routes (Router Outlet)

* Pipes
  -> {{ product.due_date | date | uppercase }} (chaining)
  -> {{ product.value | currency: 'BRL' }}

* Observables
  => Reactive programming with ReactiveX [rxjs] 
  => Observer pattern (subject detects event and notifies observer)

* Services (singletons)
  => Classes that organize and share methods and data between components 

  @Injectable({
    provideIn: "root",
  })
  export class ProductService {
    // ...
  }

* Dependency injection
  => Pattern in which the class receives dependencies from an external source instead of creating it on its own.
```