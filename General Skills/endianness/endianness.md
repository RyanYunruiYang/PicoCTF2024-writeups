# Description

# Solution:
To find the Little Endian and Big Endian representations, one can, if `word = "ibsex"`, run:
- `little_endian_hex = ''.join(format(ord(char), '02x') for char in reversed(word)).upper()`
- `big_endian_hex = ''.join(format(ord(char), '02x') for char in word).upper()`
to get the Little and Big endians.

```
Welcome to the Endian CTF!
You need to find both the little endian and big endian representations of a word.
If you get both correct, you will receive the flag.
Word: ibsex
Enter the Little Endian representation: 7865736269
Correct Little Endian representation!
Enter the Big Endian representation: 6962736578
Correct Big Endian representation!
Congratulations! You found both endian representations correctly!
Your Flag is: picoCTF{3ndi4n_sw4p_su33ess_91bc76a4}
```