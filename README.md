# Հայածրագրային Լեզուն
_hay•a•tsr•a•gay•in le•zu_
**or, the Armenian Programming Language**

This is an attempt to create a programming language based on the grammatical structure of Armenian.

## Why
Inspired by [kip](https://github.com/kip-dili/kip), I wanted to take a stab at what a programming 
language would look like if it were created according to the grammatical structure of my own native 
language. 

For myself, this is a test of system engineering. How well can I design a frankly novel programming 
language? Can I make it practical to write? Can I develop *functional* programs with it?

## Challenges
This project will present a few challenges that I am (for some at least) excited to test myself against.

1) This programming language is not written my own dialect. I speak a (predominantly) Baku-based dialect, 
while this language is written in standard Eastern Armenian. According to Armenian orthographical rules, 
one must write in the way they speak (eye dialect *is* the standard), however for the purposes of this 
project (and my own sanity) I have chosen to standardize on the national standard.

2) I have never written a programming language before. I am going in to this totally blind. We shall see 
how big of an issue that really is.

3) Armenian has no word order. I want to preserve this in the syntax of the language itself. Luckily I have 
some NLP background and have worked on tokenizers/stemmers in the past so this won't be *too* big of an issue, 
but I can still see it being annoying.

4) Grammatical exceptions. Not *too* common, but frequent enough that I will have to build it in to the 
language itself. (e.g. While words like `koshik` or `ban` would decline like `koshikits` or `banits`, words already 
ending in `-i`, like `khnotsi` would decline like `khnotsuts`)

5) The grammar itself. The definitive form of a word (in English, adding "the" in front of the word) changes 
depending on the last sound of the word it is attaching to and the first sound of the next word. If the last 
sound of the word it is modifying or the first sound of the next word is a vowel, the definitive suffix becomes `-n`. 
Otherwise, it is `-@` (the same sound as *a* in about or *u* in under). With `ban`, `ban@ mets e` but `bann e mets`. 
With `shun` and `katu`, `shun@ lav e` but `katun lav e`.

5) Claude Opus does not like Armenian text. It shits itself anytime an Armenian token is outputted (no 
more similar-character injection attacks I guess). I don't feel like dumping money in to Codex or Gemini, so 
this will have to be an undertaking of my own implement.

---

Here is an example of the code, written in Armenian script and Romanized script:

```
գլխավորել,
    «բարև աշհահր» ասեք։
վերջ։

գլխավորիր։    
```

```
// Main function
// From "glxavor" (main) + "el" (verb stem)
glxavorel,

  // "String" + aseq (say!)
  "barev ashharh" aseq.

// Function call
// Conjugating the function verb "glxavorel", replacing "el" with "ir"
// to place the verb in the imperative form
glxavorir.
```


