# ngx-translate-phraseapp


## Prerequisites

To use ngx-translate-phraseapp with your application you have to:

* Sign up for a PhraseApp account: [https://phraseapp.com/en/signup](https://phraseapp.com/en/signup)
* Use [ngx-translate](https://github.com/ngx-translate/core) module for localization in your Angular 2+ app

## Demo

You can find a demo project on [GitHub](https://github.com/phrase/ngx-translate-phraseapp-demo).

## Installation

### via NPM:

    npm install ngx-translate-phraseapp

### Build form source

You can also build it directly from source to get the latest and greatest:

    npm run dist

### Development

	npm install


### Configure

```
let config = {
  projectId: '<YOUR_PROJECT_ID>',
  phraseEnabled: true,
  phraseDecoratorPrefix: "[[__",
  phraseDecoratorSuffix: ""__]]",
  fullReparse: true
};
```

You can find the Project-ID in the Project overview in the PhraseApp Translation Center

### JavaScript snippet

Add the following snippet to your Angular app.

```js
import {PhraseAppCompiler} from 'ngx-translate-phraseapp'

let config = {
  projectId: '<YOUR_PROJECT_ID>',
  phraseEnabled: true,
  prefix: "{{__",
  suffix: "__}}",
  fullReparse: true
};
```

```js
@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    HttpClientModule,
    TranslateModule.forRoot({
      loader: {
        provide: TranslateLoader,
        useFactory: HttpLoaderFactory,
        deps: [HttpClient]
      },
      compiler: {
        provide: TranslateCompiler,
        useClass: PhraseAppCompiler
      }
    }),
  ],
  providers: [],
  bootstrap: [AppComponent]
})
```

If this does not work for you, you can also integrate the [JavaScript snippet manually](http://docs.phraseapp.com/guides/in-context-editor/custom-integration/).

## How does it work?

## Support

**Question?** Contact us at: [phraseapp.com/contact](https://phraseapp.com/contact)

**Issue?** Create a GitHub issues and share the problem
