# TIL - vim

## Line(s) spilling to a new line

```csv
ID, Name, URL, Owner
1, Johnny Sins, https://pornhub.com
, Johnny Sins
```

```
:g/^,/ . -1j
```

## Make VIM great again

```bash
sudo update-alternatives --config editor
```

## Change until _ or any other character really

```
ct_
```

## Insert new line

```
:g/.\n\n\@!/norm o
```

## Delete with pattern

```
:g/pattern/d

```

## Add text before each visually selected line(s)

```
Use CTRL+V to enter visual block mode
Move Up and/or Down
Shift+i and type text
Esc
```

## Add text to each line

```
:%s/$/pattern/
```

## Add text to visually selected line(s)

```
:'<,'>s/\%V$/,/
```

## From terminal

```bash
vim -c '%s/pattern/new-pattern/gc' file
```

## Add line number before each line

```
:%s/^/\=line('.').". "
```

## Replace every occurrence of the string ‘Ben’ by ‘Ben Rogers’ except when ‘ Rogers’ was already present

```
:s/Ben\( Rogers\)\@!/Ben Rogers/g
```

## Wrap the line between <p> and </p>

```
:s/.*/<p>\r&\r<\/p>/
```

## Replace every occurrence of the string ‘–‘ by ‘&mdash;’ in the preceding line

```
:-1s/–/\&mdash;/g
```

## Delete empty lines between lines containing <table> and </table>

```
:/<table>/,/<\/table>/g/^$/d
```

## Increment / decrement number under the cursor CTRL+A / CTRL+X

```
23
```

## Replace TODO into DONE for every line that starts with Review

```
:g/^review/s/TODO/DONE/g
```

## Ignore case when replacing

```
:%s/text/Editor/gi
```

## Number of occurrences that would be affected

```
:%s/remember/me/n
```

## Count the number of times a word occurs

```
:g/pattern/print

:g/pattern/count

:g/\cpattern/print
```


