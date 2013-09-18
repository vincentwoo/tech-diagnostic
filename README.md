Instructions
======

Hello! Please complete the following problems and send the solution to [web@everlane.com](mailto:web@everlane.com).
When you are solving the Ruby question, you may instead opt to use a language of your choice, as long as that language isn't named Java or C#.


JavaScript
======

A promise is an object which represents the future output of some computation which hasn't necessarily completed yet. We can tell the promise what to do with the output once it resolves to a concrete value by attaching success handlers. If a success handler is attached to an already resolved promise, it should execute immediately.

Implement a simple promise based callback system, with a `Promise` class that has at least the methods `success` and `resolve`.

The `success` method tells the promise what to do once it resolves to its actual value.
The `resolve` method sets the actual value onto the promise.

Example usage:

```javascript
var foo = new Promise();
var bar = new Promise();

foo.resolve('hello');

setTimeout(function(){
  bar.resolve('world');
}, 500);

foo.success(function(result){
  console.log(result);
});

bar.success(function(result){
  console.log(result);
});

// => "hello"
// ... 500ms later ...
// => "world"
```

**Nice to Have**

1. A promise should only be able to be resolved once. Subsequent calls to resolve should error.
2. A promise may have multiple success callbacks attatched.


Ruby
====

A rotational cipher, `ROT(X)`, is an ancient encoding that, given a message, returns a message where each letter has been replaced by the letter exactly `X` letters after it in the alphabet ordering. Letters near the end of the alphabet wrap around. For example, the translation table for `ROT(13)` looks like:

    ABCDEFGHIJKLMNOPQRSTUVWXYZ
    NOPQRSTUVWXYZABCDEFGHIJKLM

and therefore the message **HELLO** becomes **URYYB**

Please implement `rotx` in Ruby, which given a rotation number and a string, outputs the string rotated by that many letters. It should preserve capitalization and ignore any non-alphabetic character. It should also take a parameter that decrypts the string instead of encrypting it. For example:

```ruby
def rotx(x, string, encrypt=true)
  # Your implementation here...
end

rotx 10, 'Hello, World'
# => "Rovvy, Gybvn"
rotx 10, 'Rovvy, Gybvn', false
# => "Hello, World"

# Rotation numbers greater than 26 should work as well
rotx 36, 'Hello, World'
# => "Rovvy, Gybvn"
```
