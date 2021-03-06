# ember-cli-gravatar [![Build Status](https://travis-ci.org/johnotander/ember-cli-gravatar.svg?branch=master)](https://travis-ci.org/johnotander/ember-cli-gravatar) [![Ember Observer Score](http://emberobserver.com/badges/ember-cli-gravatar.svg)](http://emberobserver.com/addons/ember-cli-gravatar)

An [ember-cli](http://ember-cli.com) addon for a gravatar image component.

See it in action: <http://ember-cli-gravatar.divshot.io/>.

## Installation

For Ember CLI >= `0.2.3`

```
ember install ember-cli-gravatar
```

For Ember CLI < `0.2.3`

```
ember install:addon ember-cli-gravatar
```

## Usage

```hbs
{{gravatar-image email='johnotander@gmail.com'}}
```

__An example with multiple options:__

```hbs
{{gravatar-image email='johnotander@gmail.com'
  title='John Otander'
  alt='John Otander gravatar'
  defaultImage='identicon'
  class='img-circle'
  secure=false
  size=250}}
```

The default property is optional as well as the size. You can use a encoded url or a default icon name.
[Gravatar documentation](https://en.gravatar.com/site/implement/images/#default-image).

### Required

  * `email` *String* - the email for the gravatar.

### Optional

  * `class` *String* - any HTML classes to apply to the image. Default: `gravatar-image`.
  * `alt` *String* - alt description of the avatar. Default: none.
  * `size` *Number* - size of the image. Default: `250`.
  * `defaultImage` *String* - the default image to be used in case the email doesn't have a gravatar.
  * `title` *String* - the title attribute for the image. Default: none.
  * `secure` *Boolean* - whether `http` or `https` is used. Default: `true`.

### Content Security Policy

With the latest versions of the Ember CLI, you will have to whitelist gravatar.com with the following
in your `config/environment.js`:

```javascript
module.exports = function(environment) {
  // ...
  var ENV = {
    // ...
    contentSecurityPolicy: {
      'default-src': "'none'",
      'script-src': "'self'",
      'font-src': "'self'",
      'connect-src': "'self'",
      'img-src': "'self' www.gravatar.com",
      'style-src': "'self'",
      'media-src': "'self'"
    },
    // ...
  }
  // ...
};
```

## License

MIT

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

Crafted with <3 by [John Otander](http://johnotander.com).
