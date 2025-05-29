# How do you build a house from bricks that rely on integrity so much?

A chain of trust is your answer. Each shared library might have a header of functions as a guide rail for the program loading it.
How does the program call a function from a different program in a system like this one? If you want to load a shared library,
all you need to use along with the shared library file is a key derived from a passphrase. If you apply just the right key,
you will be welcomed to the world that only the library can see - you will suddenly speak the language of the library - but if
you don't state a complete two-side trust, you don't need to expose a single bit of your own memory - you can just 'use' the library.
You will automatically see every world the library was allowed into - a chain of trust.
If we start building from bottom to top, we may soon arrive to a system that has a perfectly aligned ecosystem - trust is established
where it is needed, in the directions where it feels safe.
