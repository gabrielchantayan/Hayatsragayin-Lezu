# Functions

All functions use the imperative plural (-եdelays ք) verb form. Values are passed in postfix order 
(value first, then function). Multi-argument functions use Armenian grammatical cases as parameter markers:

- **-ից (-ic)**: ablative — "from" (start point, source)
- **-ին (-in)**: dative — "to" (end point, target)
- **- delays ov (-ov)**: instrumental — "with/by" (argument, parameter)
- **-unds ards um (-um)**: locative — "in/at" (index, position)

#### Note:
The given English examples are rough translations that, given the obvious grammatical differences, 
do not capture the true essence of *hayatragayin lezu*. They are here to provide relative anchor 
points for those unfortunate enough not to speak or understand Armenian.

---

## I/O

---

### ասեք
**aseq**

Prints a value on the same line (no trailing newline).

#### Usage
```
«բարև» ասեք։
"barev" aseq.

"hello" say.
```

---

### գրեք
**greq**

Prints a value followed by a newline.

#### Usage
```
«բարև աշխարհ» գրեք։
"barev ashkharh" greq.

"hello world" write.

5 greq.
// → 5
```

---

### կարդացեք
**kardaceq**

Reads a line of input from the user. Returns a string.

#### Usage

```
«Անունդ ի՞նչ է» ասեք։
նոր տող պատասխանը կարդացեք է։

"Anund inch a?" aseq.
nor togh patasxan@ kardaceq e.

"What is your name?" say.
new string answer input is.
```

---

## Control Flow

---

### համար  ...ից  ...ին
**hamar __ic __in**

For loop. Iterates from a starting value to an ending value. The loop variable is implicitly available inside the body.

#### Usage
```
համար թիվը բան 1-ից 10-ին,
    ...
վերջ։

// Iterates from 1 to 10 on the variable "ban"
hamar tiv@ ban 1-ic 10-in,
    ...
verj.

for number foo from 1 to 10
    ...
end.
```

---

### մինչև
**minchev**

While loop. Repeats a block as long as a condition is true. Literally "until" — the block runs *while* the condition holds.

#### Usage
```
մինչև բանը փոքր է 10-ից,
    բանն է բան գումարած 1-ի
վերջ։

minchev ban@ poqr e 10-ic,
    bann e ban gumarats 1-i.
verj.

until foo is smaller from 10,
    foo is foo added by 1.
end
```

---

### եթե
**yete**

If statement. Executes a block if the condition is true.

#### Usage
```
եթե բանը մեծ է 0-ից,
    «դրական է» գրեք։
վերջ։

yete ban@ mets e 0-ic,
    "drakan e" greq.
verj.

if foo is bigger from 0
    "its positive" write.
end.
```

---

### այլ եթե
**ayl yete**

Else-if. Provides an alternative condition after a `yete` block.

#### Usage
```
այլ եթե բանը հավասար է 0-ի,
    «զերո է» գրեք։
վերջ։

ayl yete ban@ havasar e 0-i,
    "zero e" greq.
verj.

else if foo is equal to 0
    "its zero" write.
end.
```

---

### այլ
**ayl**

Else. Executes when no previous `yete` or `ayl yete` conditions matched.

#### Usage
```
այլ,
    «բացասական է» գրեք։
վերջ։

ayl,
    "bacasakan e" greq.
verj.

else,
    "its negative" write.
end.
```

#### Full if/else-if/else example
```
եթե բանը մեծ է 0-ից,
    «դրական է» գրեք։
այլ եթե բանը հավասար է 0-ի,
    «զերո է» գրեք։
այլ,
    «բացասական է» գրեք։
վերջ։

yete ban@ mets e 0-ic
    "drakan e" greq.
ayl yete ban@ havasar e 0-i,
    "zero e" greq.
ayl,
    "bacasakan e" greq.
verj.

if foo is more than 0,
    "its positive" write.
else if foo is equal to 0,
    "its zero" write.
else
    "its negative" write.
end.
```

---

### վերադարձրեք
**veradardzreq**

Returns a value from a function.

#### Usage
```
գլխավել,
    բանն է բան բազմապատկած 2—ով
    բանը վերադարձրեք։
վերջ։

glkhavel,
    bann e ban bazmapatkats 2-ov.
    ban@ veradardzreq.
verj.

to main,
    foo is foo multiplied with 2.
    foo return.
end.
```

---

### կանգեք
**kangeq**

Breaks out of the current loop.

#### Usage
```
համար թիվը բանը 1-ից 100-ին,
    եթե բանը հավասար է 50-ի,
        կանգեք.
    վերջ.
    
hamar tiv@ ban@ 1-ic 100-in,
    ete ban@ havasar e 50-i,
        kangeq.
    verj.
    
from number foo from 1 to 100,
    if foo is equal to 50,
        break.
    end.
```

---

### շարունակեք
**sharunakeq**

Skips to the next iteration of the current loop.

#### Usage
```
համար թիվը բանը 1-ից 10-ին,
    եթե բանը հավասար է 5-ի,
        շարունակեք։
    այլ,
        բանը գրեք
    վերջ։
վերջ։

hamar tiv@ ban@ 1-ic 10-in,
    ete ban@ havasar e 5-i,
        sharunakeq.
    ayl,
        ban@ greq.
    verj.
verj.
```

---