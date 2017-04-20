# query-builder

A Polymer Element that builds an elasticsearch query object using given config and data.

### Example
```js
callback = {
  dates: function(object) {
    return [object.start, object.end];
  },
  terms: function(object) {
    return object.value;
  }
};

config = {
  myStringGroup: {
    field: 'myStringField'
  },
  myNumberGroup: {
    field: 'myNumberField'
  },
  myDateGroup: {
    field: 'myDateField',
    type: 'date'
  }
};

data = {
  myStringGroup: {
    value: ['myValue']
  },
  myNumberGroup: {
    value: [1, 2]
  },
  myDateGroup: {
    start: 'myDate1',
    end: 'myDate2'
  }
};

```

```html
<query-builder 
  callback="[[callback]]"
  config="[[config]]"
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

