# common-voice-esperanto

notes and files for the esperanto version of common voice


## useful bash snippets for sentence extraction from old books

### delete all lines with less than three digits
```
awk 'length>3' alico4.txt > alico5..txt
```

### delete all lines containing w p or x
```
 sed '/[w|W|q|Q|x|X]/d' marta6.txt > marta7.txt
```

### delete long lines
```
 sed '/^.\{102\}./d' alico3.txt > alico4.txt
```

### Other useful comands
```
sed -e 's/^[ \t]*//' alico2.txt > alico3.txt
 sed '/^[[:lower:][:punct:]]/d' marta.txt > marta2.txt
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