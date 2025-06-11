# How do we mutate?
It is truly up to you how precisely you implement the mutation mechanism, but what you really must adhere to is this...
<br>Mutation mechanism shall take into account _at least_:
<br><br>1) the previous instruction
<br>2) a byte or a slice of key (derived from passkey perhaps) ... it's up to you if it's incrementally or decrementally selected bytes of key, or slices, or whatever
<br><br>
And what comes to my mind under 'what mutation means' is perhaps:
<br>
<br>scramble instructions in such a way that inside the chip's instruction decoder, the currently executed instruction is swapped with a different one that is selected
deterministically based on combination of:
<br><br>a) 'the previous instruction' (that is critical for integrity)<br>b) 'a byte or slice of key' (that is critical for irreversibility)
<br><br>(If you want, you may also incorporate some bytes from 'data section' to further support integrity, but that's up to you.)
<br><br>And of course the compiler must follow the same dance.
