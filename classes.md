# Classes and alternations
Character classes match **one** character among a certain set or range, while aleternations can match more complex cases. While classes have their own set of rules (especially about metacharacters), alternations follow the same rules of a *normal* regex.

## Character classes
`[abcde]` - match any of these chars: `a,b,c,d,e`.
`[a-e]` - match any of these chars: `a,b,c,d,e`.
`[1-6a-eA-E]` - match ints from `1` through `6`, chars from `a` through `e` (both uppercase and lowercase). Note: `'America'.match(/[a-eA-E]/)` will only match the first A and then stop looking.
`[a-e!_.?]` - match a range (`a-e`) and the chars `!` `_` `.` and `?`.
`[-_!]` - note that the dash is **not** always a special char. Here it's matched just like any other char, being at the beginning of the class.
`[^a-e]` - negate the `a-e` range, i.e. match any char that is **not** in this range.

## Alternations
`good|bad` - match either the word `good` or `bad`.
`(1|fir)st` - match either `first` or `1st`
`s(up|pid)er(monkey|man)` - match `spidermonkey`, `supermonkey`, `spiderman`, `superman`.


