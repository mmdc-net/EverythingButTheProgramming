# The Command Line
Somewhere around 1969, someone decided to replace the printer on their teletype computer terminal (known as a TTY,) with a cathode ray tube, giving birth to the "Glass TTY," perhaps the first truly modern computer interface.
With the Unix kernel came some of the first modern command line interpreters, or "shells." In 1971, Ken Thompson created "sh," also known as the "Thompson Shell."
In 1979, Stephen Bourne created the "Bourne Shell," which was generally replaced with the "Bourne again Shell," or "bash" in 1988.  Bash is still the most commonly-used shell, thirty years later,
Shells are how you interact with the part of your operating system that talks to the hardware.  In your shell, you can run commands, inspect processes, write scripts and use character-mode programs.
It's also the most efficient and powerful way of interacting with your computer.
In your shell, programs are generally written to adhere to certain principles, summarized by Peter H. Salus in A Quarter-Century of Unix (1994):

    Write programs that do one thing and do it well.
    Write programs to work together.
    Write programs to handle text streams, because that is a universal interface.

Unix-like programs take text as input and give text as output wherever possible.  They don't require extraneous interaction by default, as this would limit their usability in scripts.
They work with *pipes*. What are pipes? Pipes (Implemented with the character "|",) connect commands and programs and even let you string together lots of them, to create powerful ad-hoc programs known as *one-liners*.
