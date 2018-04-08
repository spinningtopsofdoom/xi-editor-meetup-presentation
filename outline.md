# XI Editor

!SLIDE

Pronounced Like Zigh no Zee


!SLIDE

Not
Xi  googles they do nothing
but
Why try xi?

!SLIDE

Xi is a new text editor from google

!SLIDE

As exciting as a new (Web Framework, Markup Language, JavaScript Compile to Language)

!SLIDE

Xi
Native look and feel on all devices
Fast (16ms edit and paint) and never pauses for any editing

!SLIDE

Pretty editor is secondary to the side effects it generates (e.g. Fermat's last theorem)

!SLIDE

Native look and feel means the
front end is the User Interface and paints the text
Back end holds file buffers and is responsible for editing

!SLIDE

Speed
Multiple cores for text processing
How to deal with plugins that can take up a large period of time
Plugins are a problem (lots or expensive operations)

!SLIDE

All plugins are async and communicate through JSON

!SLIDE

Equivalent to breaking SPA into series of user modules that communicate through AJAX calls

!SLIDE

how could this possibly work?

!SLIDE

Fast editing time

!SLIDE

Xi processes text using multiple cores
Need to process Line Breaks, longest line, difficultly level (ascii, code point, emoji), height, parenthesis matching

!SLIDE

Sequential stateful operations => parallel immutable opreration
Incremental updates?

!SLIDE

Map Reduce
Battleship to swat a fly

!SLIDE

Isn't that using a battleship to swat a fly?
Map Reduce is used to handle big data or in modern NOSql database
Too much over head and ceremony for a simple text editor

!SLIDE

Imperative computation
accumulator, and iterate through elements adding element to accumulator

sum = 0;
for(i =0; i &lte; n i++) {
 sum = sum + i;
}

!SLIDE

Map reduce adds two more requirements for iterative accumulation
The ability to merge two accumulators and an identity element
sum(x) + sum(y), 0
max(max(x), max(y)), 0
concat(strx), str(y)), ""

!SLIDE

The ability to merge to aggregates means we can split our sequence
XXXXXXXXXXXXXXXXXXX
AAAAAABBBBBBBCCCCCC
agg(A) + agg(B) + agg(C)

!SLIDE

Neat trick is that even though data has to be aggregated in order work does not have to happen in that order

A is slow B takes the rest of A's work
AAAAA|AAAAAA
BBBBBBBBBBBB
CCCCCCCCCCCC

!SLIDE

This is cool and all but we'll have to run map reduce every time text changes it'll be too expensive

!SLIDE

Transform computation to data structure will solve all these problems in one swoop

!SLIDE

Notice that a map reduce job is already very treeish split -> leaf, accumulation -> nodes and root

!SLIDE

f("") identity I * A = A = A * I
f(AAAA) * f(BBBB) =~ g(AAAA) * g(BBBB) mapping and reducing preserve the structure of the tree

!SLIDE

Any changes get speedy (log n) incremental updates for free since aggregates bubble up

!SLIDE

Rope data structure (it's made of many strings hahaha)

!SLIDE

We have persistent immutable text data structure easy snapshots!

!SLIDE

How I stopped worrying and Reversing Polarity

!SLIDE

Having all plugins and frontend async creates a mini version of concurrent update problem

!SLIDE

Google Wave was a similar project allowing concurrent edits of a document

"Wave took 2 years to write and if we rewrote it today, it would take almost as long to write a second time" Joseph Gentle

Newer quote https://news.ycombinator.com/item?id=12311984

!SLIDE

Making SPA web application with all modules working through ajax calls

!SLIDE

Operation Transform one solution (what Google Wave used) Instead of making change to document send operation to document

!SLIDE

ABC
Add D after A
ABDC

!SLIDE

Deletes mess this up

ABC, (1) Add 1 after A, (2) Add 2 after B, (3)Delete B
Me pearl, abraham, gummy and puffy

ABC
A1BC  (1)
A1B2C (2)
A12C  (3)

AB2C (2)
A2C  (3)
A21C (1)

!SLIDE

Problem is that deletes remove information that inserts need to correctly position themselves

!SLIDE

Reverse the polarity!
Deletes never go away they are saved.
Information only ever accumulated

!SLIDE

ABC, (1) Add 1 after A, (2) Add 2 after B, (3)Delete B

AB2C (2)
AX2C  (3)
A1X2C (1)

!SLIDE

TODO add neat stuff about CRDT

!SLIDE

Xi may be a nice shiny text editor

!SLIDE

Xi is interesting due to the ideas it explores breaking a lot of new ground

!SLIDE

Paper references

!SLIDE

Fin (possibly nerdy reference?

!SLIDE

Questions?
