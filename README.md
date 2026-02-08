
# Coded Correspondence: Caesar & Vigenère Ciphers (Python)

This project implements two classic substitution ciphers in Python:

- **Caesar cipher** — shifts each letter by a fixed offset.
- **Vigenère cipher** — shifts each letter using a repeating keyword.

The goal is educational: practice string manipulation, modular arithmetic, and writing small reusable functions.  
Spaces and punctuation are preserved so messages remain readable.

> Note: These ciphers are **not secure** and should not be used for real-world encryption.

---

## How it works

### Alphabet and indexing
All cipher logic is based on mapping letters to indices:

- `a -> 0`, `b -> 1`, ..., `z -> 25`

Shifting is done with wrap-around (mod 26).

### Caesar cipher
- **Encode**: shift each letter by `+offset`
- **Decode**: shift each letter by `-offset`

Non-letters (spaces, punctuation) are left unchanged.

### Vigenère cipher (my convention)
There are two equally valid conventions for Vigenère. In this project I use:

- **Encode**: shift each plaintext letter **backward** by the index of the corresponding key letter  
  (i.e., subtract the key index)
- **Decode**: shift each ciphertext letter **forward** by the index of the corresponding key letter  
  (i.e., add the key index)

Example idea (indices):  
If plaintext letter has index `p` and key letter has index `k`:

- `encode_index = p - k` (wrap around 0–25)
- `decode_index = c + k` (wrap around 0–25)

The keyword repeats to match the message length, and **spaces/punctuation are preserved**.

---

## Repository structure
Suggested structure:

- `notebooks/` — the main Jupyter notebook with explanations and examples
- `src/` — (optional) reusable Python functions if you later extract them from the notebook
- `tests/` — (optional) unit tests if you add them

---

## Running the notebook

### 1) Install requirements
This project only needs Jupyter to run the notebook:

```bash
pip install -r requirements.txt
