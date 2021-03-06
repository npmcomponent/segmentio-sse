*This repository is a mirror of the [component](http://component.io) module [segmentio/sse](http://github.com/segmentio/sse). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/segmentio-sse`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*

# sse

  A nice [Server-Sent Events](http://www.html5rocks.com/en/tutorials/eventsource/basics/) api

## Example

  With a SSE endpoint that responds like this:

```bash
$ curl http://localhost/updates
data: foo

data: bar

data: quit

```

  And a script that subscribes to its updates:

```js
var sse = require('sse');

var unbind = sse('/updates', function(data){
  if (data == 'quit') unbind();
  console.log(data);
});
```

  The console output will be:

    foo
    bar
    quit

## Installation

  Install with [component(1)](http://component.io):

    $ component install segmentio/sse

## API

### sse(url, fn)

  Subscribe `fn` to events on `url`. Returns an `unbind` function.

## License

  MIT
