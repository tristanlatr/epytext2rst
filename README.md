# epytext2rst
eyptext2rst is a command line tool to convert epytext markup language in RestructuredText.

Be careful when running this on code, it can do unwanted substitutions, always double check before committing. 

### General usage:

```
epytext2rst.py [-h] [-v] [-o OUTPUT] input

positional arguments:
    input input file or directory to convert

optional arguments:
    -h, --help show this help message and exit
    -v, --verbose show changes
    -o OUTPUT, --output-dir OUTPUT directory for output of parsed files
```

To convert all python files in a directory just type this:

```
python3 epytext2rst.py mydirectory -o newdirectory
```

If you just want to know what would get substituted do this:
```
python epytext2rst.py mydirectory -v
```

### Convertion:

`epytext2rst` handles the conversion of the following Epytext components:

Keywords
```
@(param|type|rtype|return|ivar) --> :(param|type|rtype|return|ivar)
```
Italics
```
I\{(.*?)\}    --> *..*
```
Bold
```
B\{(.*?)\}    --> **..**
```
Code
```
C\{(.*?)\}    --> ``...``
```
Internal links
```
L\{(.*?)\}    --> `...`
```
External links
```
U\{(.*?)\}    --> `...`_
```
