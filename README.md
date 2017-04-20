# query-builder

A Polymer Element that builds an elasticsearch query object using given config and data.

The `callback` object contains callback functions with properties defined by `callbackDates` (default `dates`) and `callbackTerms` (default `terms`) that return query terms from search objects of specific types.  The dates property contains a function that returns the two-element array of start and end dates (as date strings or null) using the given search object from `data` (or `[null, null]` by default).  The terms property contains a function that returns the array of query terms using the given search object from `data` (or `[]` by default).

The `config` object contains a collection of unique keys from `data` mapped to config objects with properties {String} `field` and (Optional) {String} `type`.  The default type is "string".  Supported types are "string" and "date".

The `data` object contains a collection of unique keys mapped to search objects with query terms.  The keys in `data` match the keys in `config`.  The search objects are sent to the `callback` functions.

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

