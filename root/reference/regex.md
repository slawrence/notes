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

## Global/Local match

* When using `match` with a regex, output differs depending on if a global flag is specified. By default, a local expression will return an array where the first position is the single matched string and the following entries are the captures (if any) specified in the expression. When a global flag is specified, all the array elements are the matched strings. In order to get the captures when using a global flag, use the `exec` function on the regex within a while loop:

`while(match = reg.exec(string) !== null)`

## Using back references in `replace`

* `"fontFamily".replace(/([A-X])/g, "-$1")` converts camel case into dot notation (`font-family`)

## Indicating a non capturing group

Parenthesis performs double duty as a grouping mechanism for operations and specifying captures. To use only as a grouping mechanism, in order to not have to sort through needless captures, a `?:` can be added right after the opening parenthesis:

* `var pattern = /((?:ninja-)+)sword/;`

## Replace with function

`replace` can use a function as its second argument to provide to determine the replacement at runtime. The following converts dash delimited strings to a camel case equivalent:

    "border-bottom-width".replace(/-(\w)/g, function (all, letter) {
        return letter.toUpperCase();
    });

This functionality can replace the `exec()` in a while loop technique. Pages 169/170 in JS Ninja document several techniques using replace to trim a string.

## Matching newlines in JS

It's often desirable to use the `.` (period) to match new lines. In js there isn't a flag to allow the operator to include newlines. This is optimally done using the following pattern:

* Example string: "<span>hello</span>\n<b>world</b>";
* This doesn't match newlines: `/.*/.exec(string)` -> "<span>hello</span>"
* This does: `/[\S\s]*/.exec(string)` -> "<span>hello</span>\n<b>world</b>"


