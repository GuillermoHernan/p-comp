# p-comp
__Process Composer:__ Language to create process architectures.

## Introduction
At this stage, the objective of this 'README' file is just to introduce the design goals for this personal project (p-comp)

## Objectives

1. Create a tool which help in creating complex process hierarchies (or architectures), leveraging the functionality of smaller processes in order to create more complex system of composed of small, reliable processes. In other words, to provide a take Unix philosophy to the next level by providing a more powerful tool to organize processes.

2. Create a language which can be used to describe protocols between processes.

3. Use the previously defined language to:
    * Check process compatibility before conecting them.
    * Validate exchanged messages.
    
4. Support current communication methods between processes.
    * The intended way is to provide adaptors to existing protocols.
    
5. Any created architecture should be possible to be used as a component of a higher-level architecture.

6. A more long-term objective is to have a graphical tool to help to create the process architectures. The rationale is that what the process script will be describing is a graph of processes. Graphs are easier to read and edit (for humans) graphically, instead of using a text based script.

## Preeliminary design

The solution will be based in creating scripts which describe process architectures.

The script interpreter will them load the processes referenced in the script, check its compatibility, start them, and establish the communication channels.

In the fisrt version, the main communication channel will be the standard input & output of the processes, which is going to be used in one of this two ways:
    
* For existing processes, adaptors will be provided to read byte or text stream input & outputs.
* For processes designed to be based on 'p-comp' protocol, the standard input & output will be used as transport protocol (which does not preclude to use others.
    
### Programming language support

The intent is to support processes written in any language, by:
* Providing adaptors to standard protocols.
* Providing libraries to use 'p-comp' protocol from different programming languages.
