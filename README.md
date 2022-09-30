# Node PKG Extractor

A simple tool to extract files and resources embedded in a Node PKG-bundled binary.
The [PKG](https://github.com/vercel/pkg) tool bundles assets inside a Virtual File System (VFS). 

It appears that both the Javascript bytecode and the original source files are includes in the VFS by default,
making it trivial to recover the source code for a PKG binary.

### Usage

```bash
$ node_pkg_extract express-example-linux-gzip
Loading binary at express-example-linux-gzip
Found PKG payload at 44728224 with size 463520
Wrote extracted file to extracted/snapshot/express/index.js
Wrote extracted file to extracted/snapshot/express/package.json
Wrote extracted file to extracted/snapshot/express/views/index.html
Wrote extracted file to extracted/snapshot/express/views/lib/sakura.css
Wrote extracted file to extracted/snapshot/express/node_modules/express/package.json
Wrote extracted file to extracted/snapshot/express/node_modules/express/index.js
```

### Help

```
usage: node_pkg_extract [-h] [--output OUTPUT] [--deobfuscate DEOBFUSCATE] binary

Extract assets from binary packed with node-pkg

positional arguments:
  binary                Node binary

optional arguments:
  -h, --help            show this help message and exit
  --output OUTPUT, -o OUTPUT
  --deobfuscate DEOBFUSCATE, -d DEOBFUSCATE
                        Deobfuscate source files. Runs command with extracted JS files. (jsattacker {file})
```