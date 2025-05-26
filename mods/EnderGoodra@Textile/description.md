# Textile
A Balatro mod that modifies the base game's `evaluate()` function, adding in some extra style options for text.

## Changes:
`{B:<integer>}` A new text style that creates a box around the selection, much like `{X: }` does for the base game. The color for the box is selected in a similar way to `{V: }`, where the provided integer acts as the index in the `colours` table, returned from `loc_vars`.

Note that this allows a box to contain only space characters if desired, unlike `{X: }` which truncates any whitespace characters present.
```lua
text = {
  'This is a {B:1,C:white}test{} for the {B:2,C:red}B{} style'
}
```
```lua
loc_vars = function(self, info_queue, card)
  return {
    vars = {
      colours = {
        G.C.SECONDARY_SET.Tarot, -- at index 1
        HEX("38000b"), -- at index 2
      },
    },
  }
end
```

`{X: }` now supports having its text color assigned using `{V: }`
```lua
text = {
  'This is a {X:1,C:white}test{} for the {X:2,V:1}X{} change'
}
```
