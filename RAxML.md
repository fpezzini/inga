RAxML
Makefile.gcc -> generates a binary called raxmlHPC
Makefile.SSE3.gcc -> generates a binary called raxmlHPC-SSE3, this is also a sequential version of RAxML that however exploits a type of very fine-grain parallelism in the processor. See here for more information on SSE3 and vector instructions.
Makefile.PTHREADS.gcc -> generates a binary called raxmlHPC-PTHREADS that can run in parallel on several cores that share the same memory (that's the case on all common multi-core desktop and laptop computers). Pthreads are a library for generating and managing a specific sort of leight-weight processes which are called threads.  
Makefile.SSE3.PTHREADS.gcc -> generates a Pthreads version called raxmlHPC-PTHREADS-SSE3 of RAxML as described above, but it also uses vector instructions within each core/processor. Usually the vectorized versions of the code (with SSE3) are faster than the non-vectorized ones because more arithmetic instructions can be executed per processor clock cycle.

In computer science, a thread of execution is the smallest sequence of programmed instructions that can be managed independently by a scheduler, which is typically a part of the operating system.


eg.
raxmlHPC-PTHREADS -T 16 -p 12345 -m PROTGAMMAWAG -s protein.phy -n T27 