---
title: "Computer Architecture Chapter 1"
date: 2021-06-19
categories: computer_architecture
---
\
Reference : Computer Organization and Design 5th edition\
\
**$ Chapter 1 Computer Abstractions and Technology $**\
\
\
**1.1 Introduction**\
\
3 different classes of copmuting applications:\
&nbsp;- Personal computers (PCs) ---> Personal mobile device (PMD)\
&nbsp;- Servers ---> Cloud computing\
&nbsp;- Embedded computers\
\
\
**1.2 Eight Great Ideas in Computer Architecture**\
\
&nbsp;1) Design for Moore's Law (Graph)\
Moore's Law : integrated circuit resources double every 18-24 months\
Computer architects must anticipate where the technology will be when the design finshes, not when it starts\
\
&nbsp;2) Use Abstraction to Simply Design (Picasso)\
Use abstractions to represent the design effectively\
\
&nbsp;3) Make the Common Case Fast (Car)\
Enhance performance better than optimizing the rare case, and is also simpler\
\
&nbsp;4) Performance via Parallism (Airplane)\
Designs that get more performance by performing operations in parallel\
\
&nbsp;5) Performance via Pipelining (Pipe)\
Pipelining : a particular pattern of parallelism\
\
&nbsp;6) Performance via Prediction (Crystall Ball)\
Sometimes it is faster if recoverable and relatively accurate\
\
&nbsp;7) Hierarchy of Memories (Pyramid)\
\
&nbsp;8) Dependability via Redundancy (Truck)\
Make systems dependable by including redundant components that can take over when a failure occurs and to help detect failures\
\
\
**1.3 Below Your Program**\
\
Hierarchy of software : (Lowest) Hardware -> Systems Software -> Applications Software\
\
Two important types of systems software : Operating System & Compiler\
&nbsp;- OS:\
interfaces between a user's program and hardware.\
Provide many services and supervisory functions\
Important functions:\
&nbsp;- Handling basic input and output operations\
&nbsp;- Allocating storage and memory\
&nbsp;- Providing for protected sharing of the computer among multiple applications using it simultaneously\
\
&nbsp;- Compilers : translate a program written in high-level languages into instructions that hardware can execute\
\
&nbsp;- The easiest signals for computers are on and off: 0 and 1 => binary numbers\
&nbsp;- Instructions are collections of bits that our computer understands and obeys\
ex) 1000110010100000 tells a computer to add two numbers\
&nbsp;- first used binary numbers (tedious)\
&nbsp; &nbsp; => invented noations and translated them to binary by hand (less, but still tedious)\
&nbsp; &nbsp; => invented a program to translate symbolic notation to binary; i.e. assember!\
&nbsp; &nbsp; ex) the programmer writes : add A,B (assembly language)\
&nbsp; &nbsp; &nbsp; &nbsp; the assember translates : 1000110010100000 (machine language)\
&nbsp; &nbsp; &nbsp; &nbsp; => now high-level prgramming languages and compilers : instructions to instructions\
&nbsp; &nbsp; &nbsp; &nbsp; ex) A + B -> add A,B -> 1000110010100000\
&nbsp; &nbsp; &nbsp; &nbsp; benefits:\
&nbsp; &nbsp; &nbsp; &nbsp; - programmers can think in a more natural language\
&nbsp; &nbsp; &nbsp; &nbsp; - languages can be designed according to their intended use\
&nbsp; &nbsp; &nbsp; &nbsp; ex) Fortran for scientific computation, Cobol for business data processing, Lisp for symbol manipulation\
&nbsp; &nbsp; &nbsp; &nbsp; - improved programmer productivity\
&nbsp; &nbsp; &nbsp; &nbsp; - allows programs to be independent of the computer on which they were developed\
&nbsp; &nbsp; &nbsp; &nbsp; (because compilers and assemblers translate to the binary!)\
\
\
**1.4 Under the Covers**\
\
Basic functions of the hardware: inputting, outputting, processing, storing data\
5 key components of a computer that performs the basic functions:\
&nbsp;1) input\
&nbsp;2) output\
&nbsp;3) memory\
&nbsp;4) datapath (called the processor with control)\
&nbsp;5) control  (called the processor with datapath)\
\
The most fascinating I/O device: graphics display\
Liquid crystal displays (LCDs)\
&nbsp;- does not produce light, but controls the transmission of light\
&nbsp;- rod-shaped molecules in a liquid bends light entering the display; rods straighten out when a current is applied and no longer bend the light\
&nbsp;- LCD displays today use an active matrix for better image quality\
&nbsp;- the image is composed of pixels\
&nbsp;- 8 bits for each of the three colors, 24bits per pixel\
&nbsp;- bit map : matrix of bits\
\
computer hardware support for graphics : raster refresh buffer (frame buffer)\
&nbsp;- image to be represented on screen is stored in the frame buffer\
&nbsp;- bit pattern per pixel is read out ot the graphics display at the refresh rate\
\
Touchscreen\
&nbsp;- today many use capccitive sensing\
&nbsp;&nbsp;- people are electrical conductors\
&nbsp;&nbsp;- if an insulator like glass is covered with a transparent conductor, touching distorts the electrostatic field of the screen\
\
\
\
-------------------------------------------\
\
Vocab\
\
Personal computers (PCs)\
: a computer for an individual, usually with a graphic display, a keyboard, and a mouse\
\
Server\
: a computer for larger programs and accessed only via a network\
\
Embedded computers\
: a computer inside another device and used for running a single or a collection of software\
\
Personal mobile device (PMD)\
: small, wireless devices to connect to the Internet (ex: smart phones, tablets)\
\
Cloud Computing\
: larger collections of servers that provide services over the Internet. Relies on giant datacenters known as Warehouse Scale Copmuters (WSCs)\
\
Software as a service (SaaS)\
: delivers software and data as a service over the Internet (ex: web search, social networking)\
\
Systems Software\
: Software that provides services that are commonly useful like operating systems, compilers, loaders, assemblers...\
\
Operating System\
: Supervising program that manages the resources of a computer for the benefit of the programs that run on that computer\
\
Compiler\
: A program that translates high-level language statements into assembly language statements\
\
Binary Digit (bit)\
: one of the two numbers in base 2 (0 or 1) that are the components of information\
\
Instruction\
: A command that computer hardware understands and obeys\
\
Assembler\
: A program that translates a symbolic version of instructions into the binary version\
\
High-level Programming Languages\
: A portable language such as C, C++, Java, or Visual Basic that is composed of words and algebraic notation that can be translated by a compiler into assembly language\
\
Input Device\
: A mechanism through which the computer is fed information, such as a keyboard\
\
Output Device\
: A mechanism that conveys the result of a computation to a user, such as a display, or to another computer\
\
Liquid Crystal Displays (LCDs)\
: A display technology using a thin layer of liquid polymers that can be used to transmit or block light according to whether a charge is applied\
\
Active Matrix Display\
: A liquid crystal display using a transistor to control the transmission of light at each individual pixel\
\
Pixel\
: The smallest individual picture element\
\
Integrated Circuit (Chip)\
: A device combining ddozens to millions of transistors\
\
Datapath\
: The component of the processor that performs arithmetic operations\
\
Control\
: The component of the processor that commands the datapath, memory, and I/O devices according to the instructions of the program\
\
Memory\
: The storage area in which programs are kept when they are running and that contains the data needed by the running programs\
\
Dynamic Random Access Memory (DRAM)\
: Memory built as an integrated circuit; it provides random access to any location.\





