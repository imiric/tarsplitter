# tarsplitter

[Download latest release](https://github.com/AQUAOSOTech/tarsplitter/releases/latest)

Safely split a large tar archive into a specified number of smaller tar archives.

- `i` - input tar archive that you want to split
- `o` - output path
- `p` - number of smaller archives to split the input archive into

```
tarsplitter -i archive.tar -o /tmp/archive-parts -p 4
```

```
archive.tar is 529479680 bytes, splitting into 4 parts of 132369920 bytes
First new archive is /tmp/archive-parts0.tar
Processed files= 10000
Processed files= 20000
Processed files= 30000
Initialized next tar archive /tmp/archive-parts1.tar
Processed files= 40000
Processed files= 50000
Processed files= 60000
Initialized next tar archive /tmp/archive-parts2.tar
Processed files= 70000
Processed files= 80000
Processed files= 90000
Initialized next tar archive /tmp/archive-parts3.tar
Processed files= 100000
Processed files= 110000
Processed files= 120000
Done reading input archive
All done
```

## Why

It is possible to split large files, such as tar archives, into parts using the `split` utility. But you need to do a little work to precompute the byte split if you want a specific number of sub-files.

```
split -b 100m archive.tar
```

Worse, `split` won't keep all the files intact. Files will be split on the line, right near byte split, span archives, possibly making the archive unusable.

`tarsplitter` will not leave any broken files between the split archives.

## Contributors

- [AQUAOSO Technologies, PBC](https://aquaoso.com)
- [Jeff Parrish](https://github.com/ruffrey)

## MIT License

See the LICENSE file in this repository.
