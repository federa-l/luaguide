### Description
A beginner's guide to Lua.

### Topics
* Disclaimers
* Files
* Comments
* Printing
* Variables
* Strings
* Numbers
* Tables
* Operators
* Math
* Statements
* Loops
* Functions
* Conversion
* Scope
* Globals
* Operating System
* Extra

# Guide
### Disclaimers
* `;` is not required in Lua and is practically ignored.
* `''` is the same thing as `""` in Lua. `''` doesn't stand for a character.
* Lua is a case sensitive language. `Lua` and `lua` are entirely different in the compiler's eyes.

### Files
File names in lua end with `.lua`. The file name doesn't commonly have an expectation like how in JavaScript they use `index.js`. If you did come across that though, they usually
utilize the file name `main.lua` or `init.lua`.

### Comments
Comments in lua begin with `--`.
```lua
-- This is a regular comment.

--[[
  This is a multi-line comment.
  What's up?
]]
```

Comments can also have `=` between `[[`.
```lua
--[=[
  This is good for ignoring multi-line strings! (We will cover those later on).
  [[ meow ]]
]=]
```

Comments with `=` between the `[[` must have the same amount of `=` in the closing `[[`. You can have any amount of `=` between the `[[`.
```lua
--[====[
  This is valid!
]====]
```

### Printing
Printing is simply done by using `print()`.
```lua
-- We are printing a number here.
print(123)

--[[
  The console will return the following:
  123
]]
```

### Variables
Variables are initiated commonly using the keyword `local`. There are also globals, but we will cover those later on.
```lua
-- This is a nil, or null variable.
local hello_world = nil
```

The keyword `nil` stands for `undefined` or `null` in Lua.

### Strings
Strings can be enveloped using `""` or `''`.
```lua
-- This is a string.
local str = 'Hello, World!'

-- This is also a string.
local strtwo = "Hello, World!"
```

Lua has a string library as well. The library can be used using `:` or `.`.
```lua
-- This is subbing in Lua.
print(string.sub('Hello, World!' , 2)) -- This will print 'ello, World!'.

-- This is also subbing in Lua.
print(('Hello World'):sub(2)) -- This will also print 'ello, World!'.

-- This is a multi-line string in Lua.
local multistr = [[
What's up?
Nothing much!
Meow.
]]

--[[
  Multi-line strings account for ALL whitespace. This means [[ hi]] will return ' hi'.
  Here's what I mean...
]]

print([[
hi there
]]) -- Returns 'hi there' with new lines above it and under it.

-- However, this will look different.
print([[
  hi there
]]) -- Returns '  hi there' with new lines above it and under it.

--[[
  As you can see, the tabs were accounted for even if it was a string. This works universally throughout your code.
  Make sure to remember this when dealing with multi-line strings.
]]
```

As I mentioned earlier, `name-calling` uses `:`. This is just you calling the function and the value you called it on being passed as the first argument/parameter.
```lua
-- This requires the manual passing of the string.
print(string.sub('Hello, World!', 2))

-- While this code uses name-calling, so we call the function on the value.
print(('Hello, World!'):sub(2))

-- This form of name-calling is more easily understandable (without the parentheses like before).
local hello_world = 'Hello, World!'

print(hello_world:sub(2))
```

The string library and can be learned about further [here](https://www.lua.org/pil/20.html).

### Numbers
Numbers don't have a specified type like `float`, `int`, or `double`. You can simply pass them as a regular variable.
```lua
-- This is a number.
print(123)

-- This is also a number.
print(12.3)

-- You can define a number using the variable syntax.
local randnumber = 123
local randnumbertwo = 12.3
```

There is no current number library, if you're excluding the `math` library, which we will cover later on.

### Tables
Arrays in Lua, or lists depending on your previous experience, are called `tables`. They use the braces syntax.
```lua
-- This is a table.
local tbl = {'hi there!', 123, true}

-- Tables can contain any value, whether it's booleans, numbers, strings, or functions.
```

A table's index starts in `1`, which is not common in other languages.
```lua
local tbl = {1, 2, 3}

print(tbl[1]) -- Returns the number '1' in the console.
```

Lua supports string indexes too. Basically these are properties of a table that have strings as names.
```lua
local tbl = {
  ['my favorite color'] = 'blue',
  1,
  true,
  500
}

-- Now we are going to index the table using the string.
print(tbl['my favorite color']) -- Returns 'blue' in the console.
```

You can also index tables using `0`, but you'd do it like you'd index a table using strings.
```lua
local tbl = { [0] = 'sup', true, 123}

print(tbl[0]) -- Returns 'sup' in the console.
```

Lua also supports hash-tables, which are tables that contain its own variables (not to be confused with variables outside of the table).
```lua
-- Our variables.
local rvar = 1
local rstr = 'Hello, World!'

-- Our table.
local tbl = {
  our_rvar = rvar,
  our_rstr = rstr,
  my_favorite_artist = 'picasso'
}

-- You'd index it like this.
print(tbl.our_rvar)

-- Or like this.
print(tbl['our_rvar'])
```





