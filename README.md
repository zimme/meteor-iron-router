Iron.Router
==============================================================================
A router that works on the server and the browser, designed specifically for [Meteor](https://github.com/meteor/meteor).

## Quick Start

Install iron-router:
```bash
> meteor add iron:router
```

Create some routes in a client/server JavaScript file:
```javascript
Router.route('/', function () {
  this.render('MyTemplate');
});

Router.route('/items', function () {
  this.render('Items');
});

Router.route('/items/:_id', function () {
  var item = Items.findOne({_id: this.params._id});
  this.render('ShowItem', {data: item});
});

Router.route('/files/:filename', function () {
  this.response.end('hi from the server\n');
}, {where: 'server'});
```

## Learning More

* Examples: Check out the [examples](https://github.com/EventedMind/iron-router/tree/devel/examples) folder.
* Guide: For more detailed explanations check out the [guides](https://eventedmind.github.io/iron-router).

## Contributing
Contributors are very welcome. There are many things you can help with,
including finding and fixing bugs, creating examples for the examples folder,
contributing to improved design or adding features. Some guidelines below:

* **Questions**: Please post to Stack Overflow and tag with `iron-router` : http://stackoverflow.com/questions/tagged/iron-router.

* **New Features**: If you'd like to work on a feature,
  start by creating a 'Feature Design: Title' issue. This will let people bat it
  around a bit before you send a full blown pull request. Also, you can create
  an issue to discuss a design even if you won't be working on it.

* **Bugs**: If you think you found a bug, please create a "reproduction." This is a small project that demonstrates the problem as concisely as possible. The project should be cloneable from Github. Any bug reports without a reproduction that don't have an obvious solution will be marked as "awaiting-reproduction" and closed after one week. Want more information on creating reproductions? Watch this video: https://www.eventedmind.com/feed/github-issues-and-reproductions.

###  Working Locally
This is useful if you're contributing code to iron-router.

  1. Set up a local packages folder
  2. Add the PACKAGE_DIRS environment variable to your .bashrc file
    - Example: `export PACKAGE_DIRS="/Users/cmather/code/packages"`
    - Screencast: https://www.eventedmind.com/posts/meteor-versioning-and-packages
  3. Clone the repository into your local packages directory
  4. Add iron-router just like any other meteor core package like this: `meteor
     add iron:router`

```bash
> git clone https://github.com/EventedMind/iron-router.git /Users/cmather/code/packages/iron:router
> cd my-project
> meteor add iron:router
```

## License
MIT
