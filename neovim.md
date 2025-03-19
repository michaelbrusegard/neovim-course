---
title: An Introduction to Neovim
author: Michael Brusegard
---

Overview
===

*If you have not installed Neovim yet, you should do so now.*

## Brief about Neovim (20 min)

# Keybindings (10 min)

## Try it out with VimTutor (25 min)

# Modes (10 min)

# Advanced tools (5 min)

# More exercises (15 min)

### Configuring Neovim and beyond (20 min)

![](./neovim.png)
<!-- end_slide -->

Brief about Neovim
===

# History & Context

- **ex**: Basic line editor, predecessor to Vi
- **Vi**: Bill Joy, 1976, introduced modal editing
- **Vim**: Bram Moolenaar, 1991, "Vi IMproved" - added features & plugins
- **Neovim**: Forked in 2014, goals: modernize, improve extensibility, collaboration and lua

## Info

Not part of GNU project.

[Primeagen Clip](https://www.youtube.com/watch?v=5Welk51oDWs&t=19s) - 0:19 - 2:16

<!-- end_slide -->

Brief about Neovim
===

# What is Neovim?

- A **text editor** manipulates plain text content
- **Word processors** (like Microsoft Word) focus on formatting
- **IDEs** (like Visual Studio) automation tools and debugger (obfuscation)

## Neovim vs. Alternatives

| Editor    | Strengths           | Weaknesses          | Best For            |
|-----------|---------------------|---------------------|---------------------|
| Neovim    | Fast, customizable  | Steep learning curve| Power users         |
| VS Code   | Extensions, UI      | Resource-heavy      | Beginners, web devs |
| Sublime   | Fast, simple        | Limited plugins     | Quick edits         |
| Emacs     | Highly customizable | Complex, key chords | Researchers         |
| IntelliJ  | Full-featured IDE   | Heavy, slow         | Java developers     |
| Notepad++ | Lightweight, simple | Windows-only        | Config edits        |

<!-- pause -->
---

### Actually Best For

| Editor    | Actually Best For                     |
|-----------|---------------------------------------|
| Neovim    | People who enjoy configuring their tools more than using them |
| VS Code   | Turning your text editor into Chrome with 50 tabs open         |
| Sublime   | People who refuse to admit VS Code exists                      |
| Emacs     | Turning your text editor into an operating system              |
| IntelliJ  | Waiting for it to load while you make coffee                   |
| Notepad++ | Editing config files you don’t understand                     |

<!-- end_slide -->

Brief about Neovim
===

# Why Learn Neovim?

- **Efficiency**: Text manipulation at the speed of thought
- **Ubiquity**: Available on virtually any Unix/Linux system
- **Transferable Skills**: Gateway to understanding other Unix tools
- **Longevity**: Skills that will last your entire career
- **Satisfaction**: Mastery is deeply rewarding

<!-- pause -->

## Limitations of Neovim

<!-- column_layout: [2, 4] -->
<!-- column: 0 -->
- Learning curve
- Terminal based
- Configuration overhead

<!-- pause -->
<!-- column: 1 -->
- High skill ceiling
- Is everywhere and good introduction to the terminal
- You know how the tool works

<!-- reset_layout -->
<!-- end_slide -->

Brief about Neovim
===

# Principles of Neovim

## Unix Philosophy

> "Do one thing and do it well"

- Neovim focuses on **text editing** and does it exceptionally
- Commands are **composable** - can be combined in powerful ways
- Examples:
  - `dw` - delete word
  - `ci"` - change inside quotes
  - `5dd` - delete 5 lines
  - `15j` - move down 15 lines

<!-- pause -->

## Modal editor

- Instead of using modifier keys (like Ctrl, Alt), uses modes
- Good for ergonomics and speed
- Basic modes:
  - **Normal mode**: Navigate and manipulate text
  - **Insert mode**: Type text (press `i` to enter)
  - **Visual mode**: Select text (press `v` to enter)
  - **Command mode**: Run commands (press `:` to enter)
  - **Replace mode**: Overwrite text (press `R` to enter)

<!-- end_slide -->

Brief about Neovim
===

# Principles of Neovim

## Tips

Basic tips to improve ergonomics

- **Rebind Caps Lock** to Esc when tapped and Ctrl when held
  - Escape is used a lot (for leaving insert mode)
  - Ctrl is used for scrolling and navigating buffers
  - Caps Lock is a useless key
- **Increase key repeat rate and lower key repeat delay** to speed up navigation
  - In the start you will most likely hold `j`/`k` to move around
- Maybe **Change to US keyboard layout**
  - Keys like `/`, `?`, `[`/`]` and `{`/`}` are easier to reach
  - Personally I bind `alt` + `'`/`o`/`a` to `æ`/`ø`/`å`

### Learn touch typing

<!-- end_slide -->

Keybindings
===

# Guess what the keybind does! (in normal mode)

- `h` | `j` | `k` | `l` - Examples: `h`, `5j`, `23k`, `3l`, `J`, `K`
<!-- pause -->
> Move left, down, up, right

<!-- pause -->
- `v` - Examples: `v20j`, `V`, `<C-v>`, `viw`
<!-- pause -->
> Visual (Enter visual mode)

<!-- pause -->
- `i` - Examples: `i`, `I`
<!-- pause -->
> Insert (Enter insert mode at start of character)

<!-- pause -->
- `a` - Examples: `a`, `A`
<!-- pause -->
> Append (Enter insert mode after character)

<!-- pause -->
- `d` - Examples: `dd`, `dw`, `d$`, `d0`, `dp`
<!-- pause -->
> Delete (Delete text based on the next motion)

<!-- pause -->
- `c` - Examples: `cc`, `C`, `cw`, `ci"`, `ca{`
<!-- pause -->
> Change (Delete text based on the next motion and enter insert mode)

<!-- pause -->
- `y` - Examples: `yy`, `yw`, `y$`, `yi)`, `y25j`
<!-- pause -->
> Yank (Copy text based on the next motion)

<!-- pause -->
- `p` - Examples: `p`, `P`
<!-- pause -->
> Paste text after cursor
<!-- end_slide -->

Keybindings
===

# Guess what the keybind does! (in normal mode)

- `u` - Examples: `u`, `<C-r>`, `U`
<!-- pause -->
> Undo the last change

<!-- pause -->
- `w` - Examples: `3w`, `W`
<!-- pause -->
> Word (Move to start of next word)

<!-- pause -->
- `e` - Examples: `e`, `2E`
<!-- pause -->
> End (Move to end of next word)

<!-- pause -->
- `b` - Examples: `5b`, `B`
<!-- pause -->
> Back (Move back to start of previous word)

<!-- pause -->
- `f` - Examples: `fa`, `f(`, `F.` (`;`, `,`)
<!-- pause -->
> Find (Find the next character and move to it)

<!-- pause -->
- `t` - Examples: `t)`, `t;`, `T,` (`;`, `,`)
<!-- pause -->
> To (Find up to the next character)

<!-- pause -->
- `r` - Examples: `ra`, `r.`, `r<space>`
<!-- pause -->
> Replace (Replace the character under the cursor)

<!-- pause -->
- `x` - Examples: `x`, `X`, `7x`
<!-- pause -->
> eXterminate (Delete character under cursor, equivalent to 'dl')
<!-- end_slide -->

Keybindings
===

# Guess what the keybind does! (in normal mode)

- `o` - Examples: `o`, `O`, `5o`
<!-- pause -->
> Open (Create a new line below cursor and enter insert mode)

<!-- pause -->
- `z` - Examples: `zz`, `zt`, `zb`, `za`
<!-- pause -->
> Screen/folds (Move screen and folds)

<!-- pause -->
- `.` - Examples: `.`
<!-- pause -->
> Repeat (Repeat the last change)

<!-- pause -->
- `/` / `?` / `#` / `*` - Examples: `/fire`, `?love`, `#`, `*`
<!-- pause -->
> Search (Searches for the sequence of characters)

<!-- pause -->
- `n` - Examples: `n`, `N`
<!-- pause -->
> Next (Go to the next search result)

<!-- pause -->
- `m` - Examples: `ma`, `mA`, `m1`
<!-- pause -->
> Mark

<!-- pause -->
- `q` - Examples: `qa`, `qa`, `q`, `@a`
<!-- pause -->
> Macro (Start recording a macro)

<!-- pause -->
- `%` - Examples: `%`
<!-- pause -->
> Jump to matching parenthesis

<!-- end_slide -->

Try it out with VimTutor
===

Now its your turn to try out Neovim!

Assuming you have Neovim installed open VimTutor by running `vimtutor` in your terminal.

Or if you have already opened Neovim, you can run `:Tutor` to open the tutor.

<!-- end_slide -->
Modes
===

# Understanding Modal Editing

- Normal mode is your "home base" - where you start and spend most time
- Think of modes as different "tools" for different jobs:
  - **Normal**: Navigation and manipulation (default mode)
  - **Insert**: Adding new text
  - **Visual**: Text selection and manipulation
  - **Command**: Running commands with `:` prefix
  - **Terminal**: Interact with integrated terminal

## Mode Transitions

- Normal → Insert: `i`, `a`, `o`, `c`...
- Insert → Normal: `<Esc>` or `<C-[>`
- Normal → Visual: `v`, `V`, or `<C-v>`
- Visual → Normal: `<Esc>` or `<C-[>`
- Normal → Command: `:`
- Command → Normal: `<Enter>` or `<Esc>`

<!-- end_slide -->

Modes
===

# The Power of Normal Mode

- Normal mode is where Neovim shines
- Combination commands follow patterns:
  - `[count][operator][motion]`
  - `[count][operator][text object]`

## Examples

- `3dw` = Delete 3 words
- `ci"` = Change text inside quotes
- `>ap` = Indent a paragraph
- `ggdG` = Delete entire file content
- `:%s/foo/bar/g` = Replace all "foo" with "bar"

<!-- pause -->

## Tips for Mode Awareness

- Status line shows current mode
- Different cursor shapes for different modes
- Develop muscle memory for `<Esc>`
- Stay in normal mode by default, enter other modes only when needed

<!-- end_slide -->

Advanced tools
===

# Working with Multiple Files

- **Buffers**: Loaded files in memory
  - `:ls` - List buffers
  - `:b [number/name]` - Switch to buffer
  - `:bd` - Delete buffes

- **Windows**: Viewports showing buffers
  - `<C-w>s` - Split horizontally
  - `<C-w>v` - Split vertically
  - `<C-w>hjkl` - Navigate windows
  - `<C-w>q` - Close window

- **Tabs**: Collections of windows (Not recommended)
  - `:tabnew` - Create new tab
  - `gt`/`gT` - Navigate tabs

<!-- end_slide -->

Advanced tools
===

# Text Objects

Text objects let you operate on semantic units of text:

- `iw`/`aw` - in word/around word
- `is`/`as` - in sentence/around sentence
- `ip`/`ap` - in paragraph/around paragraph
- `i"`/`a"` - in quotes/around quotes
- `i(`/`a(` - in parentheses/around parentheses
- `i{`/`a{` - in braces/around braces

## Examples

- `di(` - Delete everything inside parentheses
- `ci"` - Change text inside quotes
- `ya]` - Yank (copy) everything including brackets
- `vi{` - Visually select everything inside braces
- `ciq` - Change inside quotes (alternative to `ci"`)
- `dab` - Delete around brackets (includes the brackets)

<!-- end_slide -->

Advanced tools
===

# Search and Replace

- `/pattern` - Search forward
- `?pattern` - Search backward
- `*` - Search for word under cursor
- `n`/`N` - Next/previous match

## Global Search and Replace

- `:%s/old/new/g` - Replace all occurrences in file
- `:%s/old/new/gc` - Replace with confirmation
- `:5,10s/old/new/g` - Replace between lines 5-10

## Marks and Jumps

- `mx` - Set mark x
- `` `x `` - Jump to mark x
- `''` - Jump back to previous position
- `<C-o>`/`<C-i>` - Navigate jump list

<!-- end_slide -->

Advanced tools
===

# Macros & Automation

- Record a sequence of commands:
  - `qa` - Start recording to register 'a'
  - (perform actions)
  - `q` - Stop recording
  - `@a` - Execute macro 'a'
  - `5@a` - Execute macro 'a' 5 times

## Practical Example

1. `qa` - Start recording to register 'a'
2. `0f"ci"New text<Esc>j0` - Change text in quotes, move to next line
3. `q` - Stop recording
4. `10@a` - Apply changes to next 10 lines

<!-- end_slide -->

More exercises
===

# Exercise 1: Navigation Speed Drills

1. Open a large file (e.g., a log file or code file)
2. Try these navigation commands:
   - Jump to a specific line number
   - Move to the first/last line
   - Find occurrences of a specific word
   - Jump between matching brackets

<!-- pause -->

## Hints

- Jump to line 42: `42G` or `:42`
- First/last line: `gg`/`G`
- Find text: `/pattern` then `n` for next match
- Matching bracket: `%` when cursor is on a bracket

<!-- end_slide -->

More exercises
===

# Exercise 2: Text Manipulation Mastery

## Transform this list

```
apple
banana
cherry
date
elderberry
```

## Into

```
1. APPLE - fruit
2. BANANA - fruit
3. CHERRY - fruit
4. DATE - fruit
5. ELDERBERRY - fruit
```

<!-- pause -->

## Hints

- Add numbers: Use visual block mode (`<C-v>`) to select the start of each line, then `I1.<Esc>`
- Uppercase words: `gUiw` on each word or create a macro
- Add suffix: Visual block at end of each word, `$<C-v>G$A - fruit<Esc>`
- Or record a macro: `qa0i1. <Esc>gUiwA - fruit<Esc>jq` then `5@a`

<!-- end_slide -->

More exercises
===

# Exercise 3: Advanced Text Operations

## Sample text to work with

```
function calculateTotal(items) {
  let total = 0;
  for (const item of items) {
    total += item.price * item.quantity;
  }
  return total;
}
```

## Tasks

1. Change "total" to "sum" everywhere
2. Add a comment above the function
3. Indent the entire function body one more level
4. Duplicate the last line three times

<!-- pause -->

## Hints

- Replace all occurrences: `:%s/total/sum/g`
- Add comment: Move to first line, `O// Calculate the total price of items<Esc>`
- Indent block: Select with `>i{` or visual mode then `>`
- Duplicate line: `yy` then `p` multiple times or `3p`

<!-- end_slide -->

More exercises
===

# Exercise 4: Working with Multiple Lines

## Data to format

```
John, 25, Engineer
Mary, 31, Doctor
Steve, 42, Teacher
Lisa, 38, Artist
```

## Tasks

1. Sort the lines alphabetically
2. Delete all lines containing "Engineer" or "Artist"
3. Reverse the order of the remaining lines
4. Add a header row at the top
<!-- end_slide -->
Configuring Neovim and beyond (20 min)
===

## Terminology

- LSP: Language Server Protocol
- DAP: Debug Adapter Protocol
- Treesitter: Syntax highlighting
- Lazy.nvim: Plugin manager
- Buffer: An in-memory text file being edited (may not correspond to a saved file yet)
- Window: A viewport displaying a buffer
- Registers: Storage for text and commands (like clipboard)
- Lua: Programming language used for Neovim configuration
- Vim motions: normal mode commands that move the cursor

<!-- end_slide -->
Configuring Neovim and beyond (20 min)
===

# Neovim Distributions

### There are many Neovim distributions that come with pre-configured settings and plugins. Some popular ones are

- Lazyvim
- AstroVim
- NVChad

### Personally I recommend Lazyvim since it looks a lot like how you would customize Neovim yourself
<!-- end_slide -->

Configuring Neovim and beyond (20 min)
===

## Kickstart.nvim

The best starting point for learning how to configure Neovim is Kickstart.nvim. It is a large lua file with a basiv configuration and a lot of comments explaining what each part does.

If you google `Kickstart.nvim` it will probably be the first result.

[Kickstart.nvim](https://github.com/nvim-lua/kickstart.nvim)

<!-- end_slide -->
