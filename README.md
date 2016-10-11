# learning-asm

Everything has started from this tweet:

<blockquote class="twitter-tweet" data-lang="uk"><p lang="en" dir="ltr">I&#39;ve got a strong desire to learn some basics of Assembler. Can anyone suggest a good point to start from?</p>&mdash; Denys Dovhan (@denysdovhan) <a href="https://twitter.com/denysdovhan/status/784522144478879744">7 Oct 2016</a></blockquote>

In this repo I'm gonna collect links and resources, that I used for learning [Assembly][assembly].

## Get it running

I'm working on _MacBook Pro 13" early 2015_ with _macOS Siera_ and use [**nasm**][nasm]. I haven't checked that, but I think it should work on Linux too.

Probably you've already heart of [tasm], [masm] or [fasm]. To be honest, I don't know which one is better. After researching a bit, I find that [**nasm**][nasm] will be okay for me. _Maybe_. 

To install actual version of **nasm** (on my computer it was too old), type:

    $ brew install nasm

Close and reopen the terminal and you will get the new version of **nasm**, which had the critical (for macOS) `macho64` format. Execute these commands and check if you have similar output:

```
$ nasm -v
NASM version 2.12.02 compiled on Sep 14 2016
$ nasm -hf
...
    macho32   NeXTstep/OpenStep/Rhapsody/Darwin/MacOS X (i386) object files
    macho64   NeXTstep/OpenStep/Rhapsody/Darwin/MacOS X (x86_64) object files
    dbg       Trace of all info passed to output stage
...
```

## Compiling and Linking

To compile, link and run Assembly Program I use these commands:

```sh
# Generate object file from assembly:
$ nasm -f macho64 -o filename.o filename.asm

# Link object file:
ld filename.o -o filename

# Run executable:
./filename
```

_Source:_ [Running Assembly on OS X](https://lord.io/blog/2014/assembly-on-osx/)

[assembly]: https://en.m.wikipedia.org/wiki/Assembly_language
[nasm]: https://en.m.wikipedia.org/wiki/Netwide_Assembler
[tasm]: https://en.m.wikipedia.org/wiki/Turbo_Assembler
[masm]: https://en.m.wikipedia.org/wiki/Microsoft_Macro_Assembler
[fasm]: https://en.m.wikipedia.org/wiki/FASM