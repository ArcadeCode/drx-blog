+++
date = '2025-06-06T21:00:23+02:00'
draft = true
title = 'Why I Didn’t Like C - But Still See Its Value'
+++

# Why I Didn’t Like C - But Still See Its Value

## A short story about C
Before starting, please read this short introduction to the C. This language was made by Dell, the purpose was a new layer on programming level for Unix. It actually worked, a lot, for example 98.3% of the Linux Kernel was written in C :
![Github of the linux kernel mirror](/imgs/torvalds_linux_kernel_source_tree.png)

So C was really liked in the past, and we can know why, you see, before the C was the B... Yeah, our Seniors thought simple in the past ! And B was deprecated for many reasons :
- The language was very cryptic, with a complex syntaxe and hard readability.
- There was no low type structures such as `int`, `char`, `float`, ... Everything was a `int` and it's add more difficulty to this language.
- Because of the lack of low types structure, there was none `*` pointers, every pointer was a integer... You see like me was it was a bad idea.
C corrected, all this problems and added lot of helpful tool such as the preprocessor logic into the compiler with pre-processed `#instructions`.

## My First Experience with C
### Why I Started with C
Before diving into C++, I wanted to learn C. Why? I don't really know, a lot of peoples will say "Nobody need C to start a learning journey into C++" and I agree with them, C++ is a object oriented based language, but C is not like this and it's exactly what C is I really doesn't liked.

### My First Environment (WSL with Ubuntu)
My first development environment have this structure :
- **Operating System** : Windows 10
- **Coding Interface** : WSL with Ubuntu 22.14 (LTS)
- **Compiler** : [gcc](https://www.gnu.org/software/gcc/) -std=C99
- **Maker** : [CMake](https://cmake.org/)
- **IDE** : [Visual Studio Code](https://code.visualstudio.com/)

Okay first thing first... Windows is the worst of all operating software of all time to develop in C or C++,, why ? Because there is absolute zero tools to dev in C++ except Visual Studio, the lasts options is some interfaces with Linux such as VMs, Dockers, WSL or MSVC2. And I never found library already build for Windows so you need to compile all your library and Oh boy It such a crave.

> If you want to code in low languages, I highly recommend using a Linux.

> I learn C using [OpenClassroom](https://openclassrooms.com/), (this website is amazing and free).

My first occurrence with C was made using WSL, [Windows Subsystem for Linux](https://learn.microsoft.com/fr-fr/windows/wsl/) is a tool for Windows made by Microsoft to access to Linux as a subsystem into a windows, it a really useful tool made to assist developers to construct projects under Linux on Windows, you can see WSL as a solution between Virtual Machines and Docker containers. 

Using wsl is really simple, first enable wsl, by default this install Ubuntu, restart and you have ubuntu installed, now you can run it :
```sh
wsl --install
shutdown /r /t 0
wsl --set-version Ubuntu 2
wsl -d Ubuntu
sudo apt update && sudo apt upgrade -y # Update the system
sudo apt install build-essential gdb valgrind manpages-dev -y # Install C dev essentials
```

So yeah,  simple but why I've not kept this configuration ? In this time and at this day, I never changed to Neovim and always used Visual Studio Code, but the main problem is than Visual Code need a Graphic Interface Framework such as Gnome or KDE Plasma, and the setup I give you don't enable graphic interface for Ubuntu and it cost A LOT OF GO for a person who ran every week of storage on his computer. So I wanted to answer this simple question :

> Is there any solution to run my code into linux but edit it into my Windows ?

### The Problem with GUI and Visual Studio Code
So my problem was to found a solution to manager my code into my VScode, and I found two solutions :
- [WSL module](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl) for Visual Studio Code.
- [MSYS2 tool](https://www.msys2.org/) (What I choose).

I actually use Visual Studio Code, but I wanted to... yeah it a long time from now, I not realy understand why I used MSYS2 ? This was into the documentation of C/C++ developpement for Visual Studio Code. And it's keep my folders into my Windows mount and not into a special mount for my Ubuntu. The second add was the core of WSL, you see such as Docker you initialize a deamon on your computer who run during you dev session. MSYS2 doesn't do that, it run only when you execute commands or when you run one of the MSYS2 shells.

### My Switch to MSYS2
Switching to MSYS2 was realy hard for me, you see when you install MSYS2, you have no idea what MSYS2 installed, a lot of files and foldes unknow to me... Such has when I used CMake it realy irritate me. But one beautiful thing it that worked almost instantly and gave me lot of tools I've cannot run on Windows, such as `gcc` and `g++`.

This new tool was realy simple to use, it install all linux installed programs into the PATH of you system, now, juste use it on your favorite CMD :
```sh
gcc --version
```
At this time, I used this configuration :
- **Operating System** : Windows 11
- **Coding Interface** : [MSYS2](https://www.msys2.org/)
- **Compiler** : [gcc](https://www.gnu.org/software/gcc/) -std=C99
- **Maker** : [Make](https://www.gnu.org/software/make/)
- **IDE** : [Visual Studio Code](https://code.visualstudio.com/)

I've made this second configuration when I started using C++, The main change I've made is using Make has primary program maker, why ? I wanted simplicity and cmake made a lot of thing beyond his build folder and this it's what I hate the most in programming : not knowing why I have this folder here or this file here. Make just make it perfect because it was under my total control, any folder, any file, any change will be do under my control by my intentions and it was confortable for me.

## Writing Code in C
### Hello World and First Impressions
First `hello_world.c`, never skip this step !
```c
#include <stdio.h>

int main() {
    printf("Hello, world!\n");
    return 0;
}
```

### Why C Felt Tedious to Me
What I found challenging with C is that you have to explicitly tell the computer every little step it needs to perform. There’s no built-in way to group data and behavior easily like in object-oriented languages — everything is very manual and procedural.

For example:
- You write code that directly manipulates memory (the only thing I like) and variables step after step.
- There is no concept of "objects" or "methods" to abstract complexity.
- You often repeat similar code because abstractions are limited.
- The flow of the program is literally a sequence of commands the CPU will execute in order, no shortcuts.

This "step-by-step" style means you have to manage a lot of details yourself — which can be powerful but also tedious and error-prone.

## From C to C++
### What Pushed Me to Switch
I switched to C++ because I wanted to learn to construct high level structs such as Chaineds-lists, stacks, queues, ... And this was complex to made in C without a goal for this types to be declared, mainly when performing writting a new librairy.

### How C++ Solved My Pain Points
C++ is like the new C, made by Bjarne Stroustrup, it was expecially made for this, giving a renew for C who getting a little old. And it worked, C++ include in majors add Oriented Object Programming. And in the lasts versions >C++17 we have `<std::auto_ptr>`, `<std::unique_ptr>`, `<std::shared_ptr>`, Garbage collected pointers, it's not was I'm interest in C++ but this helped C++ to became more famous.


## When Would I Use C?
I cannot skip C, this is a top five of the most used languages in the world, it's a needed and used by all workers on the planet. You see I will use C++ for one thing : C is impertive oriented language. So, in some cases C can advantage me, for example into the Super Nintendo Entraiternement System (SNES), C can be easily compiled for the CPU for the SNES without need to code a lot of a game in Assembler. Maybe into this type of project I will use it, because a game is Imperative, if you know "ticks" system, you can understand why C can be use into a lot of game. If you don't, don't panick I will evenetually made a new post about this to explain how it work.

Another example is in Arduino, I don't realy use a lot of this cards as this day, but C can be realy advantagous into this type of projet.

## Final Thoughts: Is C Worth Learning?
C is not bad, in fact, it's a great language to develop in low level and he is highly optimised, I recommand it but **NOT** for all ocasions, only when you program have a goal :
- My SNES game have a goal : To end when the user finish the game or get a GameOver.
- My Arduino loop and a goal, who he try to recreat many time by seconds.

But
- My REST API doesn't have a goal, she result custom requests of the user, without knowing what to do at a specific time.
- My Website is a high level project, it don't need so low level languages, it can be to complex to develop.

As any Developper will say to you : There is no bad or good programming language, all have meaning, usefull in some projects and useless in other. It's at developers to know when to use what to perform efficiency, optimise, responses to encoured problems. I hope it will help you knowing this realy beautifull language witch is not adapted to my personals projects devlop.

## Thank you to reading
I hope this article will inspire you, thank you to reading it, it's the first "big article" I write, I'm not a native of english language, so this blog is also to train me on this language, I hope to not do lot of gramatical errors. My last phrase will be, never stop coding, nerver learning, with time and work will be a powerfull developper.