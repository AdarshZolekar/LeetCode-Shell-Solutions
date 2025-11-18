# LeetCode Shell Solutions

This repository contains my solutions to **LeetCode Shell problems**.  
The purpose of this repository is not just to provide answers but also to highlight what I learned while solving the problems.
This repo contains mainly **Bash** problems from **Leetcode**.

---

## What I Learned :

While working on these problems, I practiced and reinforced:
- **Unix pipes (`|`)** → chaining commands together
- **`grep` & regex** → filtering and matching text patterns
- **`awk`** → column-based processing
- **`sed`** → replacing text using patterns
- **`sort`, `uniq`, `tr`, `cut`** → common text manipulation tools
- Building **concise one-liner solutions** by combining tools.

---

## Example Problems :

### 1. [Valid Phone Numbers](solutions/valid-phone-numbers.sh)
```bash
grep -E '^([0-9]{3}-[0-9]{3}-[0-9]{4}|\([0-9]{3}\) [0-9]{3}-[0-9]{4})$' file.txt
```
**Key idea:** Use `grep -E` with regex to validate different phone number formats.

---

### 2. [Word Frequency](solutions/word-frequency.sh)
```bash
cat words.txt | tr -s ' ' '\n' | sort | uniq -c | sort -nr
```
**Key idea:** Convert spaces to newlines, count words with `uniq -c`, then sort by frequency.

---

### 3. [Transpose File](solutions/transpose-file.sh)
```bash
awk '{
  for (i=1; i<=NF; i++) {
    if (NR==1) { out[i]=$i }
    else { out[i]=out[i]" "$i }
  }
} END {
  for (i=1; i<=NF; i++) print out[i]
}' file.txt
```
**Key idea:** Use arrays in `awk` to re-construct rows as columns.

---

### 4. [Tenth Line](solutions/tenth-line.sh)
```bash
sed -n '10p' file.txt
```
**Key idea:** Use `sed -n '10p'` to directly print the 10th line of a file.

---

## How to Run

Clone the repo :
```bash
git clone https://github.com/AdarshZolekar/Leetcode-Shell-Solutions.git
cd leetcode-bash-solutions
```

Make scripts executable :
```bash
chmod +x solutions/*.sh
```

Run a script :
```bash
./solutions/word-frequency.sh
```

---

## License

This project is open-source under the MIT License.

---

## Contributions

Contributions are welcome!

- Open an issue for bugs or feature requests.

- Submit a pull request for improvements.

<p align="center">
  <a href="#top">
    <img src="https://img.shields.io/badge/%E2%AC%86-Back%20to%20Top-blue?style=for-the-badge" alt="Back to Top"/>
  </a>
</p>


