To create a file of the specific size in Windows:
```
fsutil file createnew <filename> <length_in_bytes>
```

To create multiple files of the specific size in Windows:
```
for /L %i in (1,1,<number_of_files>) do fsutil file createnew A%i.tmp <length_in_bytes>
```