# Angular Toastr

Application example using [Angular 12](https://angular.io/) and the [ngx-toastr](https://www.npmjs.com/package/ngx-toastr) library.

Available in:

* [GitHub Pages](https://rodrigokamada.github.io/angular-toastr/)
* [Stackblitz](https://stackblitz.com/edit/angular12-toastr)



[![Website](https://shields.braskam.com/v1/shields?name=website&format=rectangle&size=small)](https://rodrigo.kamada.com.br)
[![LinkedIn](https://shields.braskam.com/v1/shields?name=linkedin&format=rectangle&size=small)](https://www.linkedin.com/in/rodrigokamada)
[![Twitter](https://shields.braskam.com/v1/shields?name=twitter&format=rectangle&size=small&socialAccount=rodrigokamada)](https://twitter.com/rodrigokamada)



## Prerequisites

Before you start, you need to install and configure the tools:

* [git](https://git-scm.com/)
* [Node.js and npm](https://nodejs.org/)
* [Angular CLI](https://angular.io/cli)



## Getting started


**1.** Create an application with the Angular base structure using the @angular/cli com with the route file and the SCSS style format.

```shell
ng new angular-toastr
? Would you like to add Angular routing? Yes
? Which stylesheet format would you like to use? SCSS   [ https://sass-lang.com/documentation/syntax#scss                ]
CREATE angular-toastr/README.md (1003 bytes)
CREATE angular-toastr/.editorconfig (274 bytes)
CREATE angular-toastr/.gitignore (604 bytes)
CREATE angular-toastr/angular.json (3255 bytes)
CREATE angular-toastr/package.json (1076 bytes)
CREATE angular-toastr/tsconfig.json (783 bytes)
CREATE angular-toastr/.browserslistrc (703 bytes)
CREATE angular-toastr/karma.conf.js (1431 bytes)
CREATE angular-toastr/tsconfig.app.json (287 bytes)
CREATE angular-toastr/tsconfig.spec.json (333 bytes)
CREATE angular-toastr/src/favicon.ico (948 bytes)
CREATE angular-toastr/src/index.html (299 bytes)
CREATE angular-toastr/src/main.ts (372 bytes)
CREATE angular-toastr/src/polyfills.ts (2820 bytes)
CREATE angular-toastr/src/styles.scss (80 bytes)
CREATE angular-toastr/src/test.ts (743 bytes)
CREATE angular-toastr/src/assets/.gitkeep (0 bytes)
CREATE angular-toastr/src/environments/environment.prod.ts (51 bytes)
CREATE angular-toastr/src/environments/environment.ts (658 bytes)
CREATE angular-toastr/src/app/app-routing.module.ts (245 bytes)
CREATE angular-toastr/src/app/app.module.ts (393 bytes)
CREATE angular-toastr/src/app/app.component.scss (0 bytes)
CREATE angular-toastr/src/app/app.component.html (23809 bytes)
CREATE angular-toastr/src/app/app.component.spec.ts (1081 bytes)
CREATE angular-toastr/src/app/app.component.ts (219 bytes)
✔ Packages installed successfully.
    Successfully initialized git.
```

**2.** 

```shell
npm install bootstrap
```

**3.** 

```json
"styles": [
  "node_modules/bootstrap/scss/bootstrap.scss",
  "src/styles.scss"
],
"scripts": [
  "node_modules/bootstrap/dist/js/bootstrap.bundle.min.js"
]
```

**4.** Install the `ngx-toastr` library.

```shell
npm install ngx-toastr
```

**5.** Configure the `ngx-toastr` library.

```json
"styles": [
  "node_modules/bootstrap/scss/bootstrap.scss",
  "node_modules/ngx-toastr/toastr.css",
  "src/styles.scss"
],
```

**6.** 

```typescript
import { ToastrModule } from 'ngx-toastr';

imports: [
  BrowserModule,
  ToastrModule.forRoot(),
  AppRoutingModule,
],
```

**7.** 

```typescript
import { Component } from '@angular/core';
import { ToastrService } from 'ngx-toastr';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.scss'],
})
export class AppComponent {

  constructor(private toastrService: ToastrService) {
  }

  public showSuccess(): void {
    this.toastrService.success('Message Success!', 'Title Success!');
  }

  public showInfo(): void {
    this.toastrService.info('Message Info!', 'Title Info!');
  }

  public showWarning(): void {
    this.toastrService.warning('Message Warning!', 'Title Warning!');
  }

  public showError(): void {
    this.toastrService.error('Message Error!', 'Title Error!');
  }

}
```

**8.** 

```html
<div class="container-fluid py-3">
  <h1>Angular Toastr</h1>

  <div class="d-grid gap-2 col-4 mx-auto">
    <button type="button" class="btn btn-sm btn-success" (click)="showSuccess()">Success</button>
    <button type="button" class="btn btn-sm btn-info" (click)="showInfo()">Info</button>
    <button type="button" class="btn btn-sm btn-warning" (click)="showWarning()">Warning</button>
    <button type="button" class="btn btn-sm btn-danger" (click)="showError()">Error</button>
  </div>
</div>
```

**9.** 

```shell
npm start
```
