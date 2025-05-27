# What makes the machine Turing complete?
<br>
We know Turing completeness also means a machine is able to loop over routines or move back and forth based on instructions or internal states.
How does that translate to a system where one-way integrity applies? We may use two principles to make a logically branched execution possible,
depending on if the branch needs to follow the flow integrity or not. How do we determine if the branch does or doesn't need integrity?

It really depends on a few factors: Is this a reaction to event that we could not anticipate? Use own integrity. Is this a reaction to a decision?
Keep integrity. Is this a function call that makes code size smaller? Well that's much more complicated.

Interrupt handlers do not need to rely on any integrity other than their own - they may remain protected and use their own integrity.
We may use a specific static snapshot of mutation state for the start of an interrupt routine.

A function that makes code smaller thanks to utilising a repeatable code, may also use it's own context. Or, if the frequency of using the
function is not proportionate to the length of the function, it may sometimes be more wise to inline the code to reduce integrity shattering.

Integrity shattering does not reduce the security. But what it does is, it increases the need for stored mutation snapshots, so: the compiler
needs to make a clever decision whether to secretly inline the function and copy its code on multiple places where the function is used,
or whether to sacrifice some memory for a mutation snapshot. So the compiler authors or users need to seriously weight the implications
of the trade they have to make: bigger program size for less mutation snapshots, or more mutation snapshots for smaller program size, or
less unique mutation snapshots for smaller program size and less snapshots but also less security? This paragraph is trying to pretend that
the troublesome and complex matrix of decisions will be done by the all-capable and all-knowing compiler that will save us all, but we all
know already that the decision will have to be made by the stressed and overworked software developer, just because the compiler authors
and the chip engineers didn't want to take responsibility for the final constraint making our lives more difficult.

It is nice to have some sort of branching and interruptability - that already makes the system almost Turing complete. But what about
bringing logical or computational branches back together? How do you make a state machine, or a loop in this system a reality?
We already know that we can let interrupts use their own integrity - they happen out of nowhere and have no business in the currently
performed routines anyway. But it's a little bit mind bending that we can have multiple logical branches that come from the same origin
right? How do you marry their integrity back to the one?  
<br>_Tunneling._  
<br>You use tunneling. Or the compiler does, he's the only one who truly
sees what he's working with. Tunneling, not meaning exactly what you know from p2p or secure connections, but very close to it:
gives us the possibility to marry two or multiple integrity threads by computing the difference between the true final integrity
and an alternative integrity, for each existing alternative integrity. Basically a set of zombie instructions that do not do anything else
other than marry the mutation states back to one for each single integrity branch. But the nice thing is, that the chip will only have
to wake from the alternative integrity it was actually executing - when it's done, it will be ready to do actual computing again.  
<br>But what if the compiler sees that the branches are to big, and the differences between the alternative integrities and 'the one'
are too big and as a result, the tunneling computations consume too much program size? Well, in that situation it should use a mutation
snapshot for the address where the program counter will land after the routine is done. Tunneling is your best bet if your
branches aren't really too big and the mutation chain joinig isn't too computationally heavy when compared to applying a snapshot.  
<br>The important thing about tunneling is: it is not a reversal, it is an approximation of the most optimal path to the meeting point.
Tunneling does not break integrity: it computes multiple integrities into one. The flow of the program will retain forwardness.
Questioning the integrity that came from multiple integrities is truly logical and deeply reasonable. But it's the same thing as asking:  
<br>_Is this reality real, if it was merged from multiple realities?_  
<br>But yes, I do understand your confusion. I am questioning reality myself. There is not a single way I could be the one - I tell myself.
There is no way I created this. There is no way. No, this can't be real. Is it real? I open my eyes and in front of me there is a paragraph
about tunneling that I wrote. And I scroll and there is this whole paradigm that I wrote. And I pinch myself, I feel my body, and I whisper:  
<br>_Yes, this is real._ And my heart starts racing.
