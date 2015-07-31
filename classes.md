# Character classes

`[abcde]` - match any of these chars: `a,b,c,d,e`
`[a-e]` - match any of these chars: `a,b,c,d,e`
`[1-6a-eA-E]` - match ints from `1` through `6`, chars from `a` through `e` (both uppercase and lowercase). Note: `'America'.match(/[a-eA-E]/)` will only match the first A and then stop looking.
`[a-e!_.?]` - match a range (`a-e`) and the chars `!` `_` `.` and `?`
`[-_!]` - note that the dash is **not** always a special char. Here it's matched just like any other char.
`[^a-e]` - negate the `a-e` range, i.e. match any char that is **not** in this range.