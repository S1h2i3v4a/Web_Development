# 💻 Backend Terminal & Command Line Notes

Comprehensive handwritten notes, illustrated cheat sheets, and quick-reference guides for mastering the command-line interface (CLI) for backend development.

---

## 📑 Included Resources

| Resource | Description | Format / Pages | Link |
| :--- | :--- | :--- | :--- |
| **Backend Terminal Topper Notes (PDF)** | Illustrated handwritten-style notes covering core terminal concepts, command architectures, path resolution, flags, and file management. | PDF (5 Pages) | [`Backend_Terminal_Handwritten_Notes.pdf`](./Backend_Terminal_Handwritten_Notes.pdf) |
| **Interactive Printable Notes (HTML)** | Styled web view of the topper notes with responsive layout and print styling. | HTML Document | [`Backend_Terminal_Topper_Notes.html`](./Backend_Terminal_Topper_Notes.html) |

---

## 📚 Topics & Curriculum Overview

### 1. Topic 01: Core Architecture & Terminology
- **Terminal Workflow:**
  $$\text{User (Types Text)} \longrightarrow \text{Terminal (Screen/Window)} \longrightarrow \text{Shell (Interpreter)} \longrightarrow \text{OS Kernel (Executes)}$$
- **CLI (Command Line Interface):** Generic text-based interface to communicate with the OS.
- **Terminal:** The graphical wrapper / window program running the shell.
- **Console:** Low-level or physical system display for core kernel/system logs.
- **Shell:** The underlying interpreter translating commands into machine instructions.
- **Bash vs Zsh:**
  - `Bash` (*Bourne Again Shell*): Industry standard shell on Linux distributions and traditional systems.
  - `Zsh` (*Z-Shell*): Modern default shell on macOS with advanced auto-completion and customization.

---

### 2. Topic 02 & 03: Essential Navigation Commands
| Command | Full Form | Purpose | Example |
| :--- | :--- | :--- | :--- |
| `pwd` | Print Working Directory | Displays current absolute working folder path | `$ pwd` |
| `ls` | List Files | Displays all files & folders in the current directory | `$ ls` |
| `clear` | Clear Screen | Clears terminal history viewport (Shortcut: `Ctrl + L`) | `$ clear` |
| `cd <dir>` | Change Directory | Navigates into the specified folder | `$ cd backend` |
| `cd ..` | Parent Directory | Navigates one step backwards to the parent folder | `$ cd ..` |
| `cd ~` | Home Directory | Jumps directly to current user's home folder | `$ cd ~` |
| `cd /` | Root Directory | Jumps directly to base system root directory | `$ cd /` |

---

### 3. Topic 04 & 05: Path Concepts & Directory Creation
- **Absolute vs Relative Paths:**
  - **Absolute Path:** Starts from root (`/` on Unix, `C:\` on Windows) — unambiguous from anywhere.
  - **Relative Path:** Evaluated relative to the current working directory (`./` or `../`).
- **Special Path Symbols:**
  - `/` $\rightarrow$ Root directory of the file system
  - `~` $\rightarrow$ Home directory of the logged-in user
  - `.` $\rightarrow$ Current directory
  - `..` $\rightarrow$ Parent directory (one level up)
- **`mkdir` (Make Directory):**
  - Single directory: `mkdir my_project`
  - Multiple directories: `mkdir folder1 folder2 folder3`
  - Nested directory tree: `mkdir -p parent/child/subchild` (`-p` creates parent paths automatically)

---

### 4. Topic 06: Command Flags & Manual Pages (`man`)
- **Flags:** Options passed with `-` (hyphen) to customize default behavior.
- **`man <command>`:** Opens the built-in manual documentation (Press `q` to exit).
- **Common `ls` Flags:**
  - `ls -l`: Long format showing permissions, hard link count, owner, group, file size, and timestamp.
  - `ls -a`: Lists all files, including hidden dot-files (e.g. `.gitignore`, `.env`).
  - `ls -la` / `ls -al`: Combines hidden file visibility with detailed long format attributes.

---

### 5. Topic 07 & 08: File Creation & Deletion Operations
- **`touch <filename>`:**
  - Creates a new empty file with specified extension:
    ```bash
    touch index.html app.js styles.css README.md
    ```
  - *Note:* If the file already exists, `touch` will not overwrite or delete it; instead, it safely refreshes the file's access and modification timestamps.
- **File & Folder Deletion:**
  | Command | Target | Behavior / Warning |
  | :--- | :--- | :--- |
  | `rm <file>` | Files only | Deletes specified file permanently. |
  | `rmdir <dir>` | Empty directory | Deletes directory only if completely empty. |
  | `rm -rf <dir>` | Directory & Contents | Recursive (`-r`) and Forced (`-f`) deletion without prompting. |

> [!CAUTION]
> Files deleted via `rm` or `rm -rf` in the terminal **do not** go to the Recycle Bin / Trash. Deletion is immediate and irreversible. Always double-check target paths before executing `rm -rf`.
