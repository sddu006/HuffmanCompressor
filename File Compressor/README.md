## Huffman File Compressor

This project is a **file compression and decompression tool** based on the **Huffman Coding** algorithm, implemented in **C++**.

Huffman Coding is a popular lossless compression technique that assigns shorter binary codes to more frequent characters, reducing the total file size.

---

## Features

* Compress any plain text file using Huffman encoding.
* Decompress encoded files back to their original content.
* Clean and modular code (split into headers and source files).
* Easily extendable and readable.
* Built using standard C++17 — no external libraries required.

---

## 📁 Project Structure

```bash
File Compressor/
├── main.cpp                 # Entry point
├── include/
│   ├── encoder.hpp
│   ├── decoder.hpp
│   └── huffman_tree.hpp
├── src/
│   ├── encoder.cpp
│   ├── decoder.cpp
│   └── huffman_tree.cpp
├── .vscode/
│   └── tasks.json           # Build configuration for VS Code
├── test/                   # Test files and scripts
│   ├── sample.txt          # Input file
│   ├── compress.huff       # Compressed output
│   ├── decompress.txt      # Decompressed output
│   └── decode.py           # Utility to view .huff as binary
└── huffman_compressor.exe   # Output binary (after build)
```

---

## How to Build & Run

### Using VS Code (Recommended)

1. Open the `File Compressor` folder in **Visual Studio Code**.
2. Press `Ctrl + Shift + B` to **build** the project.
3. This creates an executable named:
   `huffman_compressor` (or `.exe` on Windows).
4. To run the program, use the integrated terminal:

```bash
./huffman_compressor
```

Or on Windows:

```cmd
huffman_compressor.exe
```

---

## Manual Build (without VS Code)

If you're using the terminal directly:

```bash
g++ -std=c++17 -O2 -Iinclude main.cpp src/huffman_tree.cpp src/encoder.cpp src/decoder.cpp -o huffman_compressor
```

Then run it:

```bash
./huffman_compressor
```

---

## Usage Notes

* Input/output methods (like file reading/writing) can be implemented inside `main.cpp` or `encoder.cpp/decoder.cpp`.
* Make sure the input file exists before running compression.
* You can enhance the program by adding a GUI, drag-and-drop, or web interface.

---

## Testing

The `test/` folder contains example files to test the compressor and decompressor:

* `sample.txt`: Input file to be compressed.
* `compress.huff`: Binary file generated after compression.
* `decompress.txt`: Output after decompression (should match `sample.txt`).
* `decode.py`: Python script to view the binary content of `.huff` files.

### Example: View Huffman Binary Output

Run the following Python script to view the raw binary content:

```python
with open("test/compress.huff", "rb") as f:
    byte = f.read(1)
    while byte:
        print(f'{ord(byte):08b}', end=' ')
        byte = f.read(1)
```

This helps verify the encoded bitstream during debugging.

---

## License

This project is licensed for educational and personal use. Attribution appreciated.

---

## Author

**Siddardha Tummi**
IIT Kharagpur, E&ECE
[GitHub](https://github.com/sddu006)
