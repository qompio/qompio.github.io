# QOMPIO

### We can only hope it will be good.

### 03/16/20:  
Today I took a long nap after work. I wanted to get working on getting the  MRF program but I just wasn't quite all there. So I decided to have some fun and customize my GitBash colorways and display settings.

Here is my new gitbash window:<br/>
![alt-text](https://github.com/qompio/qompio.github.io/blob/master/new_gitbash_window.jpg)


I went into the shell script for Git as found in "C:\Program Files\Git\etc\profile.d\git-prompt.sh"

In a classic fashion, I could not save my edits to the shell script file. Ofcourse, I needed admin permissions to edit the file. I opened Atom as an admin then opened the file through their navigator. The file was able to be changed and saved.

Here is the chunk of code I made the majority of changes to.
```shell
# original : PS1='\[\033]0;$TITLEPREFIX:$PWD\007\]' # set window title
# new:
PS1='\[\033]0;~| GitBash |~ ${PWD//[^[:ascii:]]/?}\007\]'
PS1="$PS1"'\n'                 # new line
PS1="$PS1"'\[\033[35m\]'       # change to magenta
PS1="$PS1"'~~Qompio~'             # ~~qompio~~
# commenting out these lines removes the mingw64
# PS1="$PS1"'\[\033[35m\]'       # change to purple
# PS1="$PS1"'$MSYSTEM '          # show MSYSTEM
# commenting these two lines out removes the path in command window
PS1="$PS1"'\[\033[33m\]'       # change to brownish yellow
PS1="$PS1"'~\W'                 # current working directory

```
I toyed with the window name:
```shell
PS1='\[\033]0;~| GitBash |~ ${PWD//[^[:ascii:]]/?}\007\]'
```
Just as some of the exampled of the things I changed, I got rid of the 'MING64' (my original reason for this entire quest) by commenting out code.
```shell
# commenting out these lines removes the mingw64
# PS1="$PS1"'\[\033[35m\]'       # change to purple
# PS1="$PS1"'$MSYSTEM '          # show MSYSTEM
```

I changed my @user/@host moniker to none other than qompio. This is also where I got into editing the text coloring. This was achieved by editing the `35` in `'\[\033[35m\]'`. Some common color numbers can be found in source 2 below. I toyed with 'lighter colorways' but I ended up deciding on the more muted color groups.


```shell
PS1="$PS1"'\[\033[35m\]'       # change to magenta
PS1="$PS1"'~~Qompio~'             # ~~qompio~~
```


I changed the a lower case w to upper case to abbreviate the working directory, which was one of my favorite customizations of the night.
```shell
PS1="$PS1"'~\W'                 # current working directory abbreviated
```

There were some other small changes I made, this can all be referenced in the sources below. Special thanks to vishnupadmanabhan for writing his tutorial up.




I used these sources:<br/>
 [source 1](https://vishnupadmanabhan.com/styling-git-bash/)<br/>
 [source 2](https://stackoverflow.com/questions/5947742/how-to-change-the-output-color-of-echo-in-linux)
