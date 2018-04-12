# angular-cartographer
Extension to Angular Maps to support complex icons and other explorations

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