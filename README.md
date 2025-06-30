# gitlite

**gitlite** is a faithful implementation of the [Write Yourself a Git](https://wyag.thb.lt/) tutorial, which recreates core Git functionality from scratch using Python and no external libraries.

This repository follows the tutorial **line by line**. The only difference is the name of the repository: `gitlite`.

---

## 🧠 Purpose

The goal of this project is to understand Git internals by manually:

- Creating and storing Git objects (blobs, trees, commits)
- Resolving references like `HEAD`, branches, and tags
- Traversing commit history manually (`log`)
- Reconstructing working trees (`checkout`)

Everything is stored in `.git/`, using Git's exact storage model.

---

## ⚙️ Requirements

- Python 3.8+
- A UNIX-like environment (as assumed in the WYAG tutorial)

---

## 🚀 Usage

This project uses a script named `wyag` — **no file extension** — just like the original tutorial.

Make sure the file is executable:

```bash
chmod +x wyag
```

Then you can run commands like:

```bash
./wyag init
echo "hello" | ./wyag hash-object -w --stdin
./wyag cat-file <hash>
```

This follows the exact instructions from the tutorial.

---

## ✅ Implemented Commands

The following commands are implemented as they appear in the tutorial:

| Command           | Description                                                  |
|------------------|--------------------------------------------------------------|
| `init`           | Initializes a Git repository by creating a `.git/` directory |
| `hash-object`    | Stores a file as a blob object and returns its SHA-1 hash    |
| `cat-file`       | Prints the content of a Git object                           |
| `write-tree`     | Creates a tree object from the working directory             |
| `commit-tree`    | Creates a commit from a tree and message                     |
| `log`            | Prints the commit history by traversing parents              |
| `rev-parse`      | Resolves refs and partial hashes to full SHA-1               |
| `ls-tree`        | Lists the content of a tree object                           |
| `checkout`       | Updates working directory based on a commit or tree          |
| `tag`            | Creates a lightweight tag pointing to a Git object           |

---

## 📂 Structure

The project is written in Python and split into modular files for readability:

```
gitlite/
├── wyag              # Main executable script (no extension)
├── objects.py        # Object read/write logic
├── refs.py           # Reference management (HEAD, tags, etc.)
├── config.py         # GitDir discovery
├── utils.py          # Compression, hashing, and path helpers
└── README.md
```

---

## 👤 Author

Created by [@dmonarchc](https://github.com/dmonarchc)  
Based entirely on the work of Thibault Polge's [Write Yourself a Git](https://wyag.thb.lt/)

---

## 🪪 License

MIT License.

