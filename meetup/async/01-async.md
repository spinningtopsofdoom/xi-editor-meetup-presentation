# Escaping the Async Maze

!SLIDE

# Single Page Application MicroServices
## Ever user has the features they want on their machine
## Communicate through websockets

!SLIDE

# Google Wave

"Wave took 2 years to write and if we rewrote it today, it would take almost as long to write a second time" Joseph Gentle

!SLIDE

# Operational Transform
## Instead of editing document send edits to document

ABC -> access document -> ABDC -> release access
ABC -> Add D after B -> ABDC

# TODO Picture

!SLIDE

# Deletes break this

ABC
(1) Add 1 after A
(2) Add 2 after B
(3) Delete B

ABC (0)
A1BC (1)
A1B2C (2)
A12C (3)

ABC (0)
AB2C (2)
A2C (3)
A21C (1)

# TODO picture

!SLIDE

# Deletes remove Information
## Edits referencing removed text non deterministic

!SLIDE

# Reverse the Polarity
## Deletes add information to the document

ABC (0)
AB2C (2)
AX2C (3)
A1X2C (1)

# TODO picture

!SLIDE

# Now edit order and aggregation don't matter
## Monotonic Join Semi Lattice
# TODO picture

!SLIDE

# TODO Xi git like merging and rebasing
