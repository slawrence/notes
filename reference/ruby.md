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

One weirdness is else ifs: notice elsif (not elseif)

    if value == true
        a = 1
    elsif
        a = 2
    end

Statement modifiers are a useful shortcut if you have a single expression:

    put "Hello, good day!" if person == "friendly"

or

    cnt = cnt + 1 while cnt < 100

Regular expression literals are placed between slashes just like js: /ab+c/

They can be matched using the =~ operator.
Strings can be replaced with the sub or gsum methods.

###Code Blocks

Code blocks are chunks of code between brackets or do and end:

    { puts "Hello" }

    do
        puts "Hello"
    end

Blocks can be "passed" to functions and executed within by the yield keyword.

    def callBlock
        yield
        yield
    end
    callBlock { puts "executing" }

produces (notice executed twice):

    executing
    executing

Parameters can be passed to blocks via yield. Within the block the params must be specified between the vertical bars:

    def callBlock
        yield "Jim"
    end

    callBlock { | name | puts name }

A iterating example:

    ['cat', 'dog', 'horse'].each do |animal|
        print animal, "food "
    end

## Classes, Objects, and Variables

    class Song
        def initialize(name)
            @name = name
        end
    end
initialize is a special method in a ruby class. It setups object state.

