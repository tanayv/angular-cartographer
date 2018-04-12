# angular-cartographer
[Angular Google Maps](https://github.com/SebastianM/angular-google-maps) mutant to support complex icons and other explorations

## Including this project in package.json
Add this under the dependencies section of your package.json file: 

```sh
"dependencies": {
    ..
    "angular-cartographer": "https://github.com/tanayv/angular-cartographer.git",
    ..
}
```

## [AGM / Angular Google Maps](https://github.com/SebastianM/angular-google-maps)
Angular Google Maps is a great component library for Google Map Components, and this repository is using the code from the [@agm/core package](https://github.com/SebastianM/angular-google-maps/tree/master/packages/core).

Agm had options for complex marker icons, which was later reverted for unknown reasons, and this repository is to use complex marker icons until the functionality is restored, and also to pursue some other explorations. This is the 
[relevant pull request](https://github.com/SebastianM/angular-google-maps/pull/1208).


## Usage

Since this project is temporary until the complex icon functionality is restored in AGM, we can use it as a direct replacement for @agm. After adding the dependency in package.json, run: 

```sh
npm install
```

Then, we must include the NgModule for Agm from the angular-cartographer mutant (as a direct replacement for @agm/core) package as follows: 

**app.module.ts**
```sh
import { NgModule } from '@angular/core';
import { AgmCoreModule } from 'angular-cartographer/core';
..

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    ..
    AgmCoreModule.forRoot({
      apiKey: '<YOUR API KEY>'
    }),
   ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

```

* **Complex Marker** \
    Complex marker functionality is useful as AGM only provides the option to set the URL of the icon, and options such as sizing, scaled sizing and anchoring for pictures aren't available. It works similar to the IconURL directive in AGM. 

    **map.component.ts**
    ```sh
    icon = {
      anchor: {x: 40, y: 40},
      labelOrigin: {x: 0, y: 0},
      origin: {x: 0, y: 0},
      scaledSize: {height: 80, width: 80},
      size: {height: 80, width: 80},
      url:'../../assets/angular.png'
    };
    lat: number = 32.884735;
    lng: number = -97.71907;
    ```

    **map.component.html**
    ```sh
    <agm-map
        [latitude]="lat"
        [longitude]="lng">
        <agm-marker 
            [latitude]="lat" 
            [longitude]="lng"
            [icon]="icon">
        </agm-marker>
    </agm-map>
    ```