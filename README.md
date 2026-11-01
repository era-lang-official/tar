# Era Tar (`github.com/era-lang-official/tar`)

POSIX ustar tape archive reader and writer for Era.

## Features
- **POSIX Format**: Fully compatible 512-byte block alignment and ustar headers.
- **Archive Generation**: `TarWriter` writes multiple files with octal headers.
- **Extraction**: `parse_tar` parses entries and file payloads.

## Usage
```era
import "github.com/era-lang-official/tar";

fn main() {
    let mut tw = TarWriter::new();
    tw.add_file("hello.txt".to_string(), "Hello Era Tar".to_string());
    let bytes = tw.serialize();
    let entries = parse_tar(bytes);
    println(entries[0].data); // "Hello Era Tar"
}
```

