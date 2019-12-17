# common-voice-files

Notes and files for common voice in German and Esperanto

## Links
* Common Voice: https://voice.mozilla.org/
* Frontend translation: https://pontoon.mozilla.org/eo/common-voice/
* Sentence Collector: https://common-voice.github.io/sentence-collector/#/
* Official promo material: https://drive.google.com/drive/folders/1RfgsCI6-rs1crh7OhlxryXO5-zN8JREr
* Zilla Slab Font: https://github.com/mozilla/zilla-slab
* Europarl dataset containing speeches from the EU in many languages: http://www.statmt.org/europarl/
* OSCAR or Open Super-large Crawled ALMAnaCH coRpus https://traces1.inria.fr/oscar/


## useful bash snippets for sentence extraction from old books

### delete all lines with less than three digits
```
awk 'length>3' alico4.txt > alico5..txt
```

### delete all lines containing certain letters
```
 sed '/[w|W|q|Q|x|X|y|Y]/d' marta6.txt > marta7.txt
 
 sed '/[ð|ð|À|Á|Â|Ã|Ä|Å|Æ|Ç|È|É|Ê|Ë|Ì|Í|İ|Î|Ï|Ð|Ñ|Ò|Ó|Ô|Õ|Ö|Ø|Ù|Ú|Û|Û|Ü|Ý|Ž|à|á|â|ã|å|æ|ç|è|é|ê|ë|ì|í|î|ï|ð|ñ|ò|ó|ô|õ|ø|ù|ú|û|ý|þ|ÿ|ā|ă|ą|ć|ċ|č|ď|đ|ē|ĕ|ė|ę|ě|ğ|ġ|ģ|ħ|ĩ|ī|ĭ|į|ı|ķ|ĸ|ĺ|ļ|ľ|ŀ|ł|ń|ņ|ņ|ṫ|š|Ў|ḃ|ḋ|ḟ|ṁ|ṗ|ṡ|ẁ|ẃ|ẅ|ẛ|ỳ|α|β|Γ|γ|Δ|δ|ε|ζ|η|Θ|θ|ι|κ|Λ|λ|μ|ν|Ξ|ξ|Π|π|ρ|Σ|σ|ς|τ]/d' europarl-de-wip.txt > eu2.txt
```

### delete long lines
```
 sed '/^.\{102\}./d' alico3.txt > alico4.txt
```

### Delete all lines with more or eqal 14 words
```
awk 'NF<=14' europarl-de-wip.txt > lees14.txt
```

### Delete all lines beginning with lower case
```
 sed '/^[[:lower:][:punct:]]/d' marta.txt > marta2.txt
```
### Delete all lines containing numbers
```
sed '/[0-9]/d' filename.txt
```

### Delete all lines containing abbreviations
```
sed '/[A-Z][A-Z]/d' europarl-de-wip.txt > eu2.txt
```

### Forgot what this does
```
sed -e 's/^[ \t]*//' alico2.txt > alico3.txt
```

### Delete lines containing slashes
```
sed '\~\/~d'  OSCAR-corpus-eo_dedup.txt > 1.txt
```

### Delete lines with some string
```
grep -v "our" t21.txt > t22.txt
```

### Delete single letters in text
```
grep -v " [fF] "
```

### 100 random sentences
```
sort -R wiki.eo.sort.txt |head -n 100 > wiki.eo.sample.txt
```

### sort alphabetical and delete dublicates
```
sort -u wiki.eo.txt > wiki.eo.sort.txt
```

### count characters
```
sed 's/\(.\)/\1\n/g' wiki.eo.txt | sort | uniq -ic > characters.eo.txt

Alternative:
awk -vFS="" '{for(i=1;i<=NF;i++)w[tolower($i)]++}END{for(i in w) print i,w[i]}' wiki.eo.no-dublicates.non-alphabetical.txt > signs.txt
```
