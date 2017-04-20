# query-builder

A Polymer Element that builds an elasticsearch query object using given config and data.

### Example
```html
<query-builder 
  callback="[[callback]]"
  config='{"myGroup":{"field":"myField"}}'
  data="[[data]]"
  query="{{query}}">
</query-builder>
```

### Dependencies

Dependencies are installed using [Bower](http://bower.io/):

    npm install -g bower
    bower install

### Testing

Tests are run using [web-component-tester](https://github.com/Polymer/web-component-tester):

    npm install -g web-component-tester
    wct

### Demonstration & Documentation

Demonstration and documentation are viewed using [polyserve](https://github.com/PolymerLabs/polyserve):

    npm install -g polyserve
    polyserve

