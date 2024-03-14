# Description:
Using a Secure Shell (SSH) is going to be pretty important.

Can you ssh as ctf-player to titan.picoctf.net at port 55352 to get the flag?

You'll also need the password 83dcefb7. If asked, accept the fingerprint with yes.

If your device doesn't have a shell, you can use: https://webshell.picoctf.org

If you're not sure what a shell is, check out our Primer: https://primer.picoctf.com/#_the_shell


# Solution:
Just follow the instructions given in the description. Running:
`ssh ctf-player@titan.picoctf.net -p 55352`

And when prompted, entering the password `83dcefb7`, wins with the flag `picoCTF{s3cur3_c0nn3ct10n_8969f7d3}`.