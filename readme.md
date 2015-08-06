# Regex reference
A quick regex reference/refresher.

## Flags
`i` - case insensitive.

## Metacharacters
`.` - any char.
`^` - any starting line.
`$` - any finishing line.
`[]` - [character class](classes.md).
`|` - *or* operator.
`()` - group `|` (*or*) expressions.
`?` - the previous char or group is an [optional item](classes.md).
`\b` - word boundary.
`?` - match the previous char or group from **0** to a max of **one** time.
`*` - match the previous char or group from **0** to as many times as possible.
`+` - match the previous char or group from **1** to as many times as possible.
`{x,y}` - match the previous char or group from **x** to a max of **y** times.

# Classes and alternations
Character classes match **one** character among a certain set or range, while aleternations can match more complex cases. While classes have their own set of rules (especially about metacharacters), alternations follow the same rules of a *normal* regex.

Unlike char classes, alternations **can't** be negated.

## Character classes
`[abcde]` - match any of these chars: `a,b,c,d,e`.
`[a-e]` - match any of these chars: `a,b,c,d,e`.
`[1-6a-eA-E]` - match ints from `1` through `6`, chars from `a` through `e` (both uppercase and lowercase). Note: `'America'.match(/[a-eA-E]/)` will only match the first A and then stop looking.
`[a-e!_.?]` - match a range (`a-e`) and the chars `!` `_` `.` and `?`.
`[-_!]` - note that the dash is **not** always a special char. Here it's matched just like any other char, being at the beginning of the class.
`[^a-e]` - negate the `a-e` range, i.e. match any char that is **not** in this range.

## Alternations
`good|bad` - match either the word 'good' or 'bad'.
`(1|fir)st` - match either 'first' or '1st'.
`s(up|pid)er(monkey|man)` - match 'spidermonkey', 'supermonkey', 'spiderman', 'superman'.
`(1[012]|[1-9])` - match either 10, 11, 12 or a single digit number > than 0. (this actually matches the hours of a clock).
`[0-5][0-9]` - match a two digit number from 00 to 59.

## Quantifiers
`rams?` - match `ram` and `rams`.
`spider(man|monkey)?` - matches 'spider', 'spiderman' or 'spidermonkey'.
`[0-9]+` - match one or more digits.
`[0-9]*` - match zero or more digits.
`[0-9]{3,5}` - match 3, 4 or 5 digits.

## Word boundaries
`\broad\b` - match 'road', discard 'roadside', 'roads', 'broad', 'abroad'.
`\b[0-9]\b` - match any isolated, one-char number, as in 'I have 1 doubt'.
