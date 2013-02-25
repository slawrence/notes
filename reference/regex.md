Regex Notes
======================

## Javascript Creation

* Literal, i.e. `var pattern = /test/`
* Constructor `var pattern = new RegExp("test")`

## Flags

* `i` - case insensitive
* `g` - match all instances vs. the default `local` which matches the first occurence
* `m` - match across multiple lines

## Set operator

* `[abc]` - match a or b or c
* `[^abc]` - match any char but a or b or c
* `[a-f]` - match a, b, c, d, e, or f

## First and last

* Caret `^` is overloaded to either anchor the match at the beginning or negate a character class set.
    * `/^test` - matches "test" but not "some test"
* `$` signifies the pattern must occur at the end.
    * `/test$/` matches "some test" but not "test me"
* `/^test$/` only matches "test"

## Repeated occurrences

* `?` signifies optional char. `/t?est` matches "test" or "est"
* `+` one or many. `/t+est/` matches "test", "tttest", but not "est"
* `*` zero or many
* `{#}` fixed number. `/t{3}est/` matches "tttest"
* `{#,#}` range - `/t{2,3}est/` matches "ttest" and "tttest"
* `{#,}` fixed to many - `/test{2,}` matches "ttest", "tttest", and so on

* Any of these operators can be "greedy" or "nongreedy". By default, they're greedy and will consume all possible chars that comprise a match. "Nongreedy" is specified by an overloaded use of the `?` character, and will only match as many as required (e.g. `/a+?/` will match "a")

## Predefined character classes

* `\t` horizontal tab
* `\b` backspace
* `\v` vertical tab
* `\f` form feed
* `\r` carriage return
* `\n` newline
* `\x0000` : `\xFFFF` unicode hexidecimal
* `\x00` : `\xFF` ASCII hexidecimal
* `.` any character except `\n`
* `\d` any decimal digit, equivalent to `[0-9]`
* `\D` any char but decimal digit, equiv `[^0-9]`
* `\w` any alphanumeric char plus underscore `[A-Za-z0-9_]`
* `\W` inverse of `\w`
* `\s` any whitespace character (space, tab, form feed, etc.)
* `\S` any char but whitespace
* `\b` word boundary
* `\B` not a word boundary

Note on word boundaries. `/\bis\b/` will only match "is" in the following string: "This island is beautiful". It doesn't match the "is" in "This" and "island", since there is not a word boundary before/after, respectively

## Grouping, Capturing, and back references

When applying operators to more than one term, the term can be grouped using parenthesis, e.g. /(test)+/ matches one or more consecutive occurences of the substring "test"

It also creates a capture, which can be backreferenced. The notation for a back reference is a backslash followed by the number of the capture to be referenced (`\1`, `\2`) This is useful for matching things like xml/html:

* `/<(\w+)>(.+)<\/\1>/` will match `<div>anything</div>`

