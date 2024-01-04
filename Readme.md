# Mine Layout Variants

Contains xkb files for my variants of the [Mine keyboard layout](https://neo-layout.org/Layouts/mine).
Only the modifier keys and layers are changed;
the letters themselves remain it the same positions, with the exception of ß.
All ideas could also be applied to the other layouts from the [Neo family](https://neo-layout.org/Layouts/).

There are three variants:

 - Mine S: Mine with symmetrically arranged modifies keys.
 - Mine S7: Seven-layer variant with a separate layer for typographical symbols.
 - Kyne: For the [Kyria](https://splitkb.com/) split keyboard.

To use the layouts, place the files in the `xkb` folder in `~/.config/xkb`.

## Mine S

![Mine S Base Layer](/images/Mine-S%20Level0%20(Standard).svg)

This variant contains two changes:
- Tab and right Mod4 (AltGr) as well as ß and left Mod4 are exchanged
  Thus the Mod4 keys end up above the Mod3 keys.
- The dash key is exchanged with dead grave, so that all accents are in the number row.

This gives a more symmetric layout and should also be more usable with a 104 key keyboard.

Having tab not in the usual place takes a bit of getting used to but it’s
not that bad.
Unfortunately, a few programs don’t behave properly and still treat the
key as tab.

## Mine S7

This variant sacrifices the dash key for another modifier key.
Tab is moved to the now free spot next to enter while AltGr becomes a new
modifier for Neo’s greek and math layers.
Thus Shift + Mod3 is free for another symbol
layer containing the “typographical” (non-programming) symbols,
which are found in various places in the Neo layouts.

We thus have three modifier keys in addition to shift,
which I call Sym (Neo Mod3), NavNum (Neo Mod4) and GreekMath,
producing the following layers:

|           |     None        |         Sym         |          NavNum        |        GreekMath       |
|----------:|:---------------:|:-------------------:|:----------------------:|:----------------------:|
| **None**  | lowercase latin | programming symbols | navigation and numbers | lowercase greek        |
| **Shift** | uppercase latin |    other symbols    |                        | uppercase greek / math |

Note: Technically, GreekMath is just Sym + NavNum because XKB doesn’t
support more than three modifiers.

### Base Layer

![Mine S7 Base Layer](/images/Mine-S7%20Level0%20(Standard).svg)

Like Mine level 1 except for the positions of the modifier keys, tab, ß
and grave.

### Uppercase Layer (Shift)

![Mine S7 Shift Layer](/images/Mine-S7%20Level1%20(Uppercase).svg)
 
Mine level 2 with the following modifications:
 - The number row contains raised numbers,
 - Shift + space = `_` (convenient for `MACRO_CASE`),
 - Shift + `,` = `…` ellipsis,
 - Shift + `.` = `’` apostrophe (or closing english single quotes).

 Admittedly, the last two look like they’re mixed up, but this way,
 the apostrophe is in the same position as its replacement character `'` on
 the symbol layer and it is not on the same finger as `t`.

### Programming Layer (Sym)

![Mine S7 Progamming Layer](/images/Mine-S7%20Level2%20(Symbols).svg)

Mine level 3 with the following modifications:
 - The number row contains lowered numbers,
 - Sym + `j` = `@` (because `…` is already on the shift layer and is not a programming symbol).

### Typographical Layer (Shift + Sym)

![Mine S7 Typographical Layer](/images/Mine-S7%20Level3%20(More%20Symbols).svg)

This layer contains currency symbols, quotation marks, 
dashes (em dash, en dash, soft hyphen, non-breaking hyphen)
and some miscellaneous symbols.
The number row contains some of the more common mathematical symbols.
Some hints to remember the positions:
 - Quotation marks are opening directly left of closing for both `„german“` and `“english”`.
   The ordering of guillemets is `«romanic»` style (looking like parantheses).
 - The em dash is on the `m`, the en dash on the `n`.
 - The non-breaking hyphen is on the same key as the usual hyphen.

### Navigation and Number Layer (NavNum)

![Mine S7 NavNum Layer](/images/Mine-S7%20Level4%20(NavNum).svg)

Mine level 4 with the following modifications:
 - I’ve changed the symbols the right hand can type in an attempt to
 make them as useful as possible for calculator-like applications.
 The spanish `¿`, `¡` must now be typed with `♫+?+?`, `♫+!+!`.

### Greek Layer (GreekMath)

![Mine S7 Greek Layer](/images/Mine-S7%20Level6%20(Greek).svg)

Mine level 5, except that I’ve moved the kappa variant `ϰ` to the `ü` key
(and I’ve added the pi variant `ϖ` on `v`)
and made the number row all math symbols.

### Math Layer (Shift + GreekMath)

![Mine S7 Math Layer](/images/Mine-S7%20Level7%20(Math).svg)

Same as Mine level 6.

Note: There are too many math symbols to have keys for them all
with a finite number of layers, let alone to remember their positions.
I therefore find it more useful to use compose.
The programming layer offers many of the “ingredients” as well as the
compose key, so many symbols can be typed with this layer alone, e.g.
`± ∓ ≤ ≥ → ← ≔ ≕ ⊢ ⊨ ÷ ‖ ≈ ≅ ≠ ⊳ ⊲`.
For the math symbols on the number row of the typographical and greek
layers, I’ve mostly chosen some which can’t be done this way
or have not so natural compose sequences.

## Kyne

The Kyria is a split keyboard without a number row.
While numbers are already available in Neo,
some typographical symbols are lost,
which was the original motivation for the typographical layer,
even though I now like it also on usual keyboards for the
more logical arrangement.

The Kyne layout uses the seven layers of Mine S7 plus three more.
The GreekMath modifier is now called Var because it can also combine
with NavNum to yield a layer for function keys, media and bluetooth
control.
Neo’s math layer is split up into a separate uppercase greek and two
math layers.
This gives:

|          |     None        |       Shift     |         Sym         |     Shift + Sym     |        NavNum           |
|---------:|:---------------:|:---------------:|:-------------------:|:-------------------:|:-----------------------:|
| **None** | lowercase latin | uppercase latin | programming symbols |    other symbols    | navigation and numbers  |
| **Var**  | lowercase greek | uppercase greek |    math symbols     |  more math symbols  | media and function keys |

All modifiers are on thumbs with Var on the right hand and the others on the left hand.
Sym is above Shift and the two can be easily pressed together.

The NavNum key is implemented directly in the keyboard firmware,
because the layers correspond to keys that are usually physical keys on a keyboard and layout-independent.
Having them in the firmware makes the keyboard minimally usable with any layout.
Also, XKB supports only three modifier keys.

![]("/images/Kyne%20Level0%20(Standard).svg")
![]("/images/Kyne%20Level1%20(Uppercase).svg")
![]("/images/Kyne%20Level2%20(Programming).svg")
![]("/images/Kyne%20Level3%20(Typographical).svg")
The typographical layer includes the accents that are usually found on Neo level 4.
![]("/images/Kyne%20Level4%20(NavNum).svg")
Here, Kyne differs a bit from Mine S7, particularly for the bottom row of the left hand.
This is convenient for programming when locking in the layer:
One can navigate with the arrows, select code with Shift and have cut, copy, paste at
a single keystroke.
I would do the same in Mine S7, but XKB doesn’t seem to be able to simulate Ctrl
and the direct Cut, Copy, Paste codes are not used by many application.
![]("/images/Kyne%20Level5%20(Greek).svg")
![]("/images/Kyne%20Level6%20(Uppercase%20Greek).svg")
![]("/images/Kyne%20Level7%20(Math).svg")
Math layers are not yet done.
![]("/images/Kyne%20Level8%20(Math%202).svg")
![]("/images/Kyne%20Level9%20(Function).svg")
