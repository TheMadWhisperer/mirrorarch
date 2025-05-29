# How does a mirrorarch know things?
It all seems like a mysterious cloud of events now. Like a timeline of happenings. A chain of statements that are never understood and yet somehow always have an impact.
How does it know things? How does it tend to its truths and secrets? You remember [mirrormachine](https://github.com/TheMadWhisperer/mirrormachine)? Yes, I remember too.
You may encrypt data via the very same model that has lead to mirrorarch: This is an ideal way to store developer specific signatures, becuase program mutation fingerprint
together with the fignature is impossible to forge... You probably already see the truth: mirrormachine can be used to store program data: The data section be encrypted
by instructions that can be brought to life only with those who have the right incantation. The code section can be used to generate a combination of program and develper
signature and can be encrypted at the beginning of the executable in such a way that: a) users can easily verify the authenticity of the program b) a program loader may verify
the program integrity before loading the code.
It's a little paradoxical, right? We're using the integrity to encrypt a proof of its authenticity. I promise there is more to it. A clever assembler might create a starting
block of rubbish logical instructions from naturally sourced entropy, and those could be used to encrypt signature into the data section. Then a tunnel may be used to
marry the rubbish with the entry point of the program => integrity is not broken, no disruption of spacetime, everyone is happy. Each block of rubbish instructions will
be specific to each run of assembly of course. This is going to be a nightmare for attackers to reverse engineer: all they will see will be encoded data of an executable
file, and if they are lucky, maybe they will have the key derived from a passkey, but you guess correctly: that is not so easy to get in this system. And even if they did
have the key: they will never know if the encrypted bytes they see came from this instruction combined with this signature byte, or if it was a million of different
combinations, and we're still stuck at the fist byte...
