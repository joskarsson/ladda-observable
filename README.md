![ladda-observable](https://smallimprovementstech.files.wordpress.com/2017/03/laddalogo-horiz-color-21.png)

![Build status](https://api.travis-ci.org/ladda-js/ladda-observable.svg?branch=master)
[![Coverage Status](https://coveralls.io/repos/github/ladda-js/ladda-observable/badge.svg?branch=master&cache=1)](https://coveralls.io/github/ladda-js/ladda-observable?branch=master)

# ladda-observable

A [Ladda](https://github.com/ladda-js/ladda) plugin to allow to create
observables on all `READ` operation.

## How to use
The observable plugin should work directly with your existing Ladda configuration. However you need to make sure you have the following things configured:
- API-functions need the operation set to `READ` to be observable.
- The other API-functions for the same Entity also need operations set for the observable to be notified of changes.

An observable can then be created by calling `createObservable` on the API-function to make it observable. You can subscribe to an observable using `subscribe()`. It takes a callback which is called whenever the entity updates. (The callback is called immediately after subscribing, performing an initial `READ` operation if needed.)
```javascript
observable.subscribe(callback);
```

`subscribe()` returns a disposable reference that you can use to `unsubscribe()` to the observable.
```javascript
const disposable = observable.subscribe(callback);
...
disposable.unsubscribe();
```

The `subscribe()` method also takes a second callback which is called when an error occurs.
```javascript
observable.subscribe(changeCallback, errorCallback);
```

## Contribute

Please let us know if you have any feedback. Fork the repo, create Pull Requests and Issues.
