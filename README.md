# orgs

store, retrieve, delete, and search [org:Organization](http://www.w3.org/TR/vocab-org/#org:Organization)s using [levelgraph-jsonld](https://github.com/mcollina/levelgraph-jsonld)

## methods

```
var level = require('level');
var db = level('./mydb');
var orgs = require('orgs')(db, opts);
```

### orgs.put(obj, function (err, obj) {

Storing organizations is extremely easy:
```javascript
var wbcg = {
  "@id": "https://web-payments.org#org",
  "name": "Web Payments Community Group",
  "homepage": "https://web-payments.org"
};

orgs.put(wbcg, function(err, obj) {
  // do something after the obj is inserted
});
```

### orgs.get(id, function (err, obj) {

Retrieving a JSON-LD object from the store requires its `'@id'`:
```javascript
orgs.get(wbcg['@id'], function(err, obj) {
  // obj will be the very same of the wbcg object
});
```

### orgs.del(id, function (err) {

In order to delete an object, you can just pass it's `'@id'` to the
`'@del'` method:
```javascript
orgs.del(wbcg['@id'], function(err) {
  // do something after it is deleted!
});
```

### orgs.search(constraints, function (err, solution) {

```
TODO
```

## license

MIT
