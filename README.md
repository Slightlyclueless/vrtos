# VRTOS
A rust based RTOS (Real-Time Operating System). Because I might actually be slightly stupid (Or crazy, take your pick)

This for the time being is an RTOS targeting X86_64 architecture for the time being, future architectures depend on what I actually need to put this pile of crap on.

_This project was written without the assistance of GitHub CodeStealer, OpenAI's ChatGPThief, or other similar content-stealing predictive algorithms._

# Project Outline

This RTOS will only have the one dependency, UEFI-RS, this crate basically abstracts away all the UEFI boilerplate (I'm crazy not masochistic).

The basic outline of this will be an event driven, memory confined RTOS. The RTOS will primarily schedule new tasks via a priority order, however tasks of the same priority level will be scheduled sequentially (This does mean however, that the onus is on the programmer to correctly prioritize tasks).

Memory managment of this will be very specific, each application *and* the kernel will have it's own memory stack, compeletely seperate of each other with no memory cross communication.

# Project Layout

 - `boot` : the UEFI bootloader. Not Supporting Secure boot for the time being, because I looked into that and fuck no.
 - `kernel` : The kernel. It's a kernel.
 - `qemu` : Building the OS and running it under QEMU + OVMF.
