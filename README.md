# jos-mit-lab

My implementation of the JOS operating system and kernel, following the MIT 6.828 Operating System Engineering labs.

This repository contains my solutions and modifications across labs, covering booting, memory management, process isolation, system calls, file systems, and networking on x86.

Focused on understanding low-level system design and kernel development from first principles.


### To build kernel again

From your project directory:
```
docker run -it --rm -u $(id -u):$(id -g) -v $(pwd):/jos jos-env
```
Then inside:
```
cd /jos
make
make qemu-nox
```
You don’t need to rebuild unless you changed code.
#### Important mental model (this will save you later)
Every time you run:
make qemu-nox
you are:
> booting a **fresh virtual PC from scratch**

Nothing persists inside JOS unless you explicitly modify disk images.
So:
- All processes (`envs`) restart
- Shell resets
- Filesystem reloads from image
#### To exit

```
Ctrl + A
X

then 
I have no name!@542d992da23e:/jos$ exit
```

