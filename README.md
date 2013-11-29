simple-cw-titanium
==================

A simple ChatWork API client for Titanium. ( **UNOFFICIAL** )

## Installation

copy `lib` directory into `Resources` directory.

```
PROJECT_DIR/
    Resources/
        lib/ (HERE!!!)
        app.js
    tiapp.xml

```

### Dependencies

* [lodash](https://github.com/lodash/lodash)
* [underscore.deferred](https://github.com/wookiehangover/underscore.Deferred)

## API Document

[Official API Document](http://developer.chatwork.com/ja/)

[RAML](https://github.com/chatwork/api)

## Usage

The minimal you'll need to have is:

```js
var CW = require('/lib/vendor/simple-cw-titanium/chatwork'),
    client = CW();

// initialize.
client.init({ token: 'YOUR_TOKEN' });

// get your info.
client.get('me', function (err, res) {
    console.log(res.body);
});

// create room.
client.post('rooms', {
    name: 'room',
    members_admin_ids: '123456789,987654321',
    description: 'description'
}, function (err, res) {
    console.log('created.');
});
```

### Deferred support

```js
var CW = require('/lib/vendor/simple-cw-titanium/chatwork'),
    client = CW(),
    Deferred = client.Deferred;

// initialize.
client.init({ token: 'YOUR_TOKEN' });

// get your info.
client
    .get('me')
    .done(function (res) {
        console.log(res.body)
    })
    .fail(function (err) {
        console.error(err);
    });
```

## Author

* [astronaughts](https://twitter.com/astronaughts)