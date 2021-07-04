Zsh Note 
============================================================

Install Zsh ( source code with root access )
------------------------------------------------------------

### Download the source code
`wget -O zsh.tar.xz https://sourceforge.net/projects/zsh/files/latest/download`  
This will downloard `zsh.tar.xz` in current folder  

### Extract `zsh.tar.xz`  
`unxz zsh.tar.xz && tar -xvf zsh.tar`  

### Install
```
cd <source_code_folder>
./configure — prefix=$HOME
make && make install
```

### Edit `.bashrc`  
```
[ -f $HOME/bin/zsh ] && exec $HOME/bin/zsh -l
```




