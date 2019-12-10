# common-voice-esperanto

notes and files for the esperanto version of common voice

## Links
* Common Voice in Esperanto: https://voice.mozilla.org/eo
* Frontend translation: https://pontoon.mozilla.org/eo/common-voice/
* Sentence Collector: https://common-voice.github.io/sentence-collector/#/
* Official promo material: https://drive.google.com/drive/folders/1RfgsCI6-rs1crh7OhlxryXO5-zN8JREr
* Zilla Slab Font: https://github.com/mozilla/zilla-slab



## useful bash snippets for sentence extraction from old books

### delete all lines with less than three digits
```
awk 'length>3' alico4.txt > alico5..txt
```

### delete all lines containing w, q, x or y
```
 sed '/[w|W|q|Q|x|X|y|Y]/d' marta6.txt > marta7.txt
```

### delete long lines
```
 sed '/^.\{102\}./d' alico3.txt > alico4.txt
```

### Delete all lines beginning with lower case
```
 sed '/^[[:lower:][:punct:]]/d' marta.txt > marta2.txt
```
### Delete all lines containing numbers
```
sed '/[0-9]/d' filename.txt
```

### Other useful comands
```
sed -e 's/^[ \t]*//' alico2.txt > alico3.txt
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