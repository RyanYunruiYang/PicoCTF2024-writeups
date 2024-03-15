# Description

# Solution:
NOTE: Running the `guessing_game.sh` file locally doesn't work. I did this and it failed. You have ssh into the portal they give you.

Binary search! My oracle told me:
- Higher than 500
- Higher than 750
- Higher than 875
- Lower than 937 (range is now [876, 936])
- Higher than 906 (range is now [907, 936])
- Lower than 921 (range is now [907, 920])
- Lower than 913 (range is now [907, 912])
- Higher than 910 (range is now [911, 912])

A relatively efficient way to do this is to have a Desmos calculator up, with variables $l, r$ representing the lower and upper bounds, and a value $$m = \frac{l+r}{2}$$. Regardless of how you compute the median of the current valid range, the final solution is `picoCTF{g00d_gu355_ee8225d0}`.