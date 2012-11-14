# Christian Neukirchen's Ruby Style Guide

This is a fork of Christian Neukirchen's Ruby Style Guide, with some of my
personal preferences. The original can be found
[here](https://github.com/chneukirchen/styleguide).


## Formatting:

* Use ASCII (or UTF-8, if you have to).

* Use 2 space indent, no tabs.

* Use Unix-style line endings.

* Use spaces around operators, after commas, colons and semicolons,
  around { and before }.

* No spaces after (, [ and before ], ).

* Indent when as deep as case.

* Use an empty line before the return value of a method (unless it
  only has one line), and an empty line between defs.

* Use RDoc and its conventions for API documentation.  Don't put an
  empty line between the comment block and the def.

* Use empty lines to break up a long method into logical paragraphs.

* Keep lines fewer than 80 characters.

* Avoid trailing whitespace like the plague.


## Syntax:

* Use def with parentheses when there are arguments.

* Never use for, unless you exactly know why.

* Avoid multiline ?:, use if.

* Use parentheses when calling methods when they're worded as commands or look
  like "functions". For example:
    ```Ruby
    x = Math.sin(y)
    user = User.find(3)
    point.translate(0, 1)
    ```
  Avoid parentheses when the method call has a DSL feel and is alone on the
  line, like:
    ```Ruby
    has_many :users
    link_to "Foo", bar_path
    collection.include? 3
    ```
* Avoid return where not required.

* Avoid line continuation (\) where not required.

* Using the return value of = is okay:

    ```Ruby
    if v = array.grep(/foo/) ... 
    ```

* Use ||= freely.

* Use non-OO regexps (they won't make the code better).  Freely use
  =~, $0-9, $~, $` and $' when needed.


## Naming:

* Use snake_case for methods.

* Use CamelCase for classes and modules.  (Keep acronyms like HTTP,
  RFC, XML uppercase.)

* The length of an identifier determines its scope.  Use one-letter
  variables for short block/method parameters, according to this
  scheme:

    a,b,c: any object
    d: directory names
    e: elements of an Enumerable
    ex: rescued exceptions
    f: files and file names
    i,j: indexes
    k: the key part of a hash entry
    m: methods
    o: any object
    r: return values of short methods
    s: strings
    v: any value
    v: the value part of a hash entry
    x,y,z: numbers

  And in general, the first letter of the class name if all objects
  are of that type.

* Use _ or names prefixed with _ for unused variables.

* When using inject with short blocks, name the arguments |a, e|
  (mnemonic: accumulator, element)

* When defining binary operators, name the argument "other".

* Prefer map over collect, find over detect, find_all over select,
  size over length.


## Comments:

* Comments longer than a sentence are capitalized and use punctuation.

* Avoid superfluous comments.


## The rest:

* Avoid long methods.

* Avoid long parameter lists.

* Add "global" methods to Kernel (if you have to) and make them private.

* Use OptionParser for parsing complex command line options and
  ruby -s for trivial command line options.

* Write for 1.8, but avoid doing things you know that will break in 1.9.

* Avoid needless metaprogramming.


## General:

* Code in a functional way, avoid mutation when it makes sense.

* Do not mutate arguments unless that is the purpose of the method.

* Do not mess around in core classes when writing libraries.

* Do not program defensively.
  (See http://www.erlang.se/doc/programming_rules.shtml#HDR11.)

* Keep the code simple.

* Don't overdesign.

* Don't underdesign.

* Avoid bugs.

* Read other style guides and apply the parts that don't dissent with
  this list.

* Be consistent.

* Use common sense.
