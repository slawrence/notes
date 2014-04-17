Bash Notes
====================

### Unix/Window file format stuff (these progs may not always be available)

`file <filename>` General info about a file
`d2u <filename>` Convert CRLF to LF (win to unix)

### List the top 20 largest files in a directory

`du -a /folder | grep -v "not filter" | grep "filter" | sort -n -r | head -20

### Sed examples

`sed -i.bak s/STRING_TO_REPLACE/REPLACEMENT/g file.txt` - Find and replace with backup

### Grep examples

`grep -lr text_or_regex_to_search * | grep -v ".svn"` - Grep recursively, only listing files, ignoring .svn
