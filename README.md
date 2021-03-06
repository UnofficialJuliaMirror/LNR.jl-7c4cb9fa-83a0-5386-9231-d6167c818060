# LNR

LNR.jl implements a `LineNumberingReader` type which transparently wraps any other reader (`::IO`). It's intended for working with hand written text where line and column information is significant, and provides functions for working with this information.

`LineNumberingReader`s can be created with either an IO object or a string as a parameter.

The `Cursor` type, which has the `line` and `column` fields, represents a position between two characters (and not the character itself). So `Cursor(n, m)` represents the position just before the `m`th character on line `n`. Comparisons are supported.

The `cursor` function gives the current position in the stream as a cursor. `seek` can be called as usual, but with a `Cursor` instead of an integer, to set the reader at any position in the file.

Other than that, standard IO functions are wrapped, so you can use a line reader as you would any other stream.
