# Escaping the Async Maze

!SLIDE

# Single Page Application MicroServices
## Ever user has the features they want on their machine
## Communicate through websockets

!SLIDE

# Google Wave

### "Wave took 2 years to write and if we rewrote it today, it would take almost as long to write a second time" Joseph Gentle

!SLIDE

# Operational Transform
## Instead of editing document send edits to document

![operational transform](../../images/operational_transform.png)

!SLIDE

# Deletes break this

![operational transform delete](../../images/operational_transform_delete.png)

!SLIDE

# Deletes remove Information
## Edits referencing removed text non deterministic

!SLIDE

# Reverse the Polarity
## Deletes add information to the document

![crdt tombstone](../../images/crdt_tombstone.png)

!SLIDE

# Now edit order and aggregation don't matter
## Monotonic Join Semi Lattice
# TODO picture

!SLIDE

# TODO Xi git like merging and rebasing
