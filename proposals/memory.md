# How does a mirrorarch know things?
It all seems like a mysterious cloud of events now. Like a timeline of happenings. A chain of statements that are never understood and yet somehow always have an impact.
How does it know things? How does it tend to its truths and secrets?<br><br>You remember [mirrormachine](https://github.com/TheMadWhisperer/mirrormachine)? Yes, I remember too. You probably already see the truth: mirrormachine can be used to store program data: The data section can be encrypted
by instructions that can be brought to life only by those who have the right incantation. The code section can be used to generate a combination of program and develper
signatures and can be encrypted inside a special section of the executable in such a way that:<br><br>a) users can easily verify the authenticity of the program<br>b) a program loader may verify
the program integrity before loading the code.<br><br>
It's a little paradoxical, right? We're using the integrity to encrypt a proof of its authenticity. I promise there is more to it. A clever assembler might create a starting
block of rubbish NOP instructions (potentially multiple variations with NOP behavior) from naturally sourced entropy, and those could be used to encrypt signature into the data section. Then a tunnel may be used to
marry the rubbish with the entry point of the program => integrity is not broken, no disruption of spacetime, everyone is happy. Each block of rubbish NOP instructions will
be specific to each run of assembly of course. This is going to be a nightmare for attackers to reverse engineer: all they will see will be encoded data of an executable
file, and if they are lucky, maybe they will have the key derived from a passkey, but you guess correctly: that is not so easy to get in this system.<br><br>And even if they did
have the key: they will never know if a concrete encrypted byte came from a concrete instruction and signature byte or if it was a different combination, and we're still
considering the fist byte... They can get nowhere even if they have an open source assembler.<br><br>
But yes, memory can be shared between shared objects and programs depending on how the trust is established: buffers may be encrypted in some protected section of RAM, and even if they are already
accessed in a protected section, they will be 1:1 understandable only by those who speak the language of the process hosting the buffer. RAM could theoretically be accessed
as "just another memory page", and each RAM page could be encrypted in the same way as the program data, but this comes with a challenge: malicious users may try to flood
RAM by forcing the program to allocate more memory and they may try to find patterns, which opens an attack vector that does not exist without this way of RAM paging.<br><br>BUT:
There is a way how to hide patterns even in repetitive data (and please keep in mind this specific technique is just an idealistic draft and not something you must adhere to when
designing a system): a trusted incorruptible on-chip source of entropy can be used to obfuscate the predictability of data - and those can be encrypted just like program data.
