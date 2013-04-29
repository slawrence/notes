Ruby Notes
==============

Parenthesis around arguments aren't necessary. Need to look into precedence rules but looks like it's best to use parenthesis in all but the simplest of cases.

Variables don't have to be declared.

Semi-colons are not required.

Brackets are not used. Instead blocks are ended with `end`

#This is a comment
# Multi-line comments are commonly done this
# way, but there is also the ability to do the
# following:

=begin
multi
line
comment
is ignored, kind of weird
=end

String literals with double quotes are processed more than single quotes. Ruby looks for escape sequences and variables can be inserted via #{var-name}.

def sayHello(name)
    return "Hello #{name}"
end
myName = 'Sean'
puts sayHello(myName);

Looks like there are implicit replies. Last expression evaluated in a function is returned:

def saySomething()
    "Apple"
end

There are conventions when it comes to variable and class names.

local
$global
@instance
@@class
CONSTANT
ClassNames #Upper case 1st char

Hashes and Arrays are pretty similiar. The difference is only and integer can be used as an index for an Array. They can store heterogeneous data.
