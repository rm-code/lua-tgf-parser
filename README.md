# lua-tgf-parser
A parser for the "[Trivial Graph Format](https://en.wikipedia.org/wiki/Trivial_Graph_Format)" (TGF) written in Lua.

## Usage

Parsing an example .tgf file like this:
```tgf
1 LEFT
2 RIGHT
#
1 2 LTR
2 1 RTL
```

Would work like this:
```lua
local TGFParser = require( 'TGFParser' )

local graph = TGFParser.parse( 'example.tgf' )

for _, node in ipairs( graph.nodes ) do
    print( node.id, node.label )
end

for _, edge in ipairs( graph.edges ) do
    print( edge.from, edge.to, edge.label )
end
```

The above script would give you this console output:
```
1	LEFT
2	RIGHT
1	2	LTR
2	1	RTL
```
